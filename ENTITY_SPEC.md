# SCAR TISSUE — Entity Behavior Spec ("The Understudy")

*The Understudy is the Chorus's physical expression. It is not a predator that happens to be scary. It is a being that **feels the player's pain** and is drawn to it. Its behavior must therefore be readable, fair, and emotionally legible.*

---

## 1. Design Intent

| Goal | Implementation |
|---|---|
| The player's body is the AI's input | Entity senses a **Pain Signature**, not just sight/sound. |
| Readable | Every state has a visible and audible **tell**. |
| Fair | The player can always reason: "I'm hurt, so it found me." |
| Not a pure chaser | The entity can be *calmed* by good care. |
| Emotional | It is sympathetic, drawn to pain and unsettled by comfort. |

**What it is not:** An omniscient hunter, a jump-scare dispenser, or a rubber-banding difficulty tool.

---

## 2. Sensing Model

The entity does **not** use line-of-sight as its main sense.

### 2.1 Pain Signature (PS)
A continuous 0–100 value computed from the player's body each frame:

```
PS = Σ over zones ( wound_intensity[z] × zone_weight[z] × state_multiplier )
     + scar_resonance
     + recent_hurt_pulse (decays over ~20s)
```

- `wound_intensity`: fresh/bleeding wounds high, stabilized medium, healing low, clean 0.
- `zone_weight`: legs/torso 1.0, hands 0.8, head 1.2, eyes/ears 0.6.
- `state_multiplier`: Bleeding ×1.5, Infected ×1.3, Untreated ×1.2, Stabilized ×0.6.
- `scar_resonance`: small constant per scar (the Chorus recognizes old pain), capped.
- `recent_hurt_pulse`: spikes when the player takes damage, decaying exponentially.

### 2.2 Perceived Distance
The entity "feels" PS through the building's nerve-tissue network, so detection range scales with PS and **is bent by water and structure**:
```
detect_range = base_range × (PS / 100) × medium_factor
medium_factor: water 1.5, wet tile 1.2, dry floor 1.0, wood/insulated 0.7
```
Water carries pain further, and the player can learn this and use it.

### 2.3 Secondary senses
- **Hearing:** footsteps and loud actions add to a `Noise` value that raises agitation and gives a target location (inaccurate by ±distance).
- **Sight:** weak. Used only to confirm a target already felt.
- **Care sense:** well-performed treatment emits a **Comfort** value that *reduces* its agitation (see §5).

---

## 3. State Machine

```
DORMANT → DRAWN → MIRRORING → APPROACHING → CONTACT → SOOTHED → (DORMANT)
              ↑          ↓          ↓            ↓
              └─────── LOST ←───────┴────────────┘
```

| State | Trigger | Behavior | **Tell (visual/audio)** |
|---|---|---|---|
| **DORMANT** | PS below threshold or player out of range | Stands in an anchor pose in the environment; faint breathing layer | Distant breathing, a "held" posture |
| **DRAWN** | PS above threshold within `detect_range` | Moves slowly toward the *felt pain location*; stops often; head tilts | Footprints appear; breath synchronizes slightly with player's |
| **MIRRORING** | Within medium distance (≈10–20m) | Copies the player's gait, limp, and posture with a half-beat delay; does not attack | Echo footsteps; matching wound shown on its body |
| **APPROACHING** | Agitation high (high PS + noise + no Comfort) | Closes distance deliberately, still mirroring | Breath goes ragged; audio "doubles" |
| **CONTACT** | Within arm's reach and agitated | Delivers a **zone-specific injury** (matching a vulnerable zone) in a telegraphed attack | 1.2s wind-up: shoulders drop, head tilts, low tone swells |
| **SOOTHED** | Player applies treatment nearby or stays still and calm, with Comfort high | Entity pauses, then drifts back to anchor | Breathing slows; posture relaxes |
| **LOST** | Player breaks detection (PS low, noise low, out of range) | Searches last felt location, then returns to DORMANT | Head sweeps; breath quiets |

**Early-game restriction:** In the vertical slice (Wards 1–2), the entity is capped at **MIRRORING** during the first half and **APPROACHING** only on the catwalk. CONTACT is disabled until Ward 3.

---

## 4. Mirroring System (Signature Feature)

The entity's animation is **procedural**, driven by player body state. This makes the player's injuries visible *on the monster*.

| Player state | Entity mirror |
|---|---|
| Leg limp | Same limp, ~0.4s delayed |
| Hand wound | Raises/holds matching hand |
| Crouch | Lowers, head tracking |
| Stillness | Freezes in sympathy |
| Ear damage | Entity's breath *loses the echo*, forcing the player to rely on visual tells |
| Sprint | Entity does **not** sprint; it *lengthens its stride* and gains ground unpredictably |

**Why it matters:** The player learns to read themselves *through* the entity, and can use it as a diagnostic ("it's limping, so my leg is worse than I thought").

---

## 5. Care Resonance (Mechanic Supporting the Release Ending)

Treatment quality emits **Comfort**:
```
Comfort += treatment_quality × proximity_factor   (on completing treatment)
agitation -= Comfort × decay_rate                 (while in range)
```
- A clean, careful treatment *near* the entity reduces agitation and can push it to SOOTHED.
- Rushed or poor treatment adds little or no Comfort.
- This allows a **non-violent, skill-based approach** to encounters: stay calm, treat well, let it feel relief.
- Tracked silently as the "Compassion" component of the ending tracker.

**Fairness check:** The player can discover this naturally. After the first SOOTHED moment (the Ward 2 catwalk lights), a Ward 3 recording hints at it.

---

## 6. Attack Design (From Ward 3)

- **Targeted zones:** Prefers the zone the player is already hurt in (limp → leg, cut hand → hand). It "feels" there first, so hits are **predictable**.
- **Telegraph:** 1.2s wind-up with audio swell. Player may dodge, block (scar-dependent), or break line by closing a door.
- **Damage:** One zone injury per CONTACT, never instant death. Severity scales with agitation.
- **Recovery window:** After CONTACT it **recoils** for 3–5s (it feels the hurt it caused), giving the player a chance to flee.
- **Death condition:** Only from accumulated vital-state thresholds (see GDD fail state), never from a single hit.

---

## 7. Difficulty & Fairness Rules

1. **No cheating.** The entity never reads hidden player position beyond what PS + noise implies.
2. **No rubber-banding.** Difficulty is not secretly adjusted. The Mercy Dial scales injury severity and detection range, and is disclosed.
3. **Always escapable.** Every encounter space has at least one non-lethal route (door, water, stillness, care).
4. **Always telegraphed.** No attack without a wind-up and a tell.
5. **Quiet windows.** After CONTACT or a chase, enforce a minimum calm period (≥45s of DORMANT/LOST behavior).
6. **Predictable seeds.** Core behavior has deterministic rules with limited variance, so players can learn.

### Tunable parameters (data-driven)
| Param | Default | Range | Notes |
|---|---|---|---|
| `base_range` | 20m | 10–40 | Detection scale |
| `ps_threshold_drawn` | 15 | 5–30 | Low PS = ignored |
| `mirror_delay` | 0.4s | 0.2–0.8 | Longer = easier to read |
| `agitation_rise_rate` | 1.0 | 0.5–2.0 | Mercy Dial scales |
| `comfort_decay_rate` | 0.5 | 0.2–1.0 | How fast care calms |
| `contact_windup` | 1.2s | 0.8–2.0 | Telegraph time |
| `recoil_time` | 4s | 2–6 | Escape window |
| `calm_window_min` | 45s | 30–90 | Anti-fatigue |

---

## 8. Technical Notes

### Perception pseudo-code
```
each tick:
  PS = compute_pain_signature(player.body)
  noise = player.noise_level
  range = base_range * (PS/100) * medium_factor(player.position)
  dist = distance(entity, player)

  if dist <= range or noise_heard:
      agitation += agitation_rise_rate * f(PS, noise) * dt
  agitation -= comfort * comfort_decay_rate * dt
  agitation = clamp(agitation, 0, 100)

  state = next_state(state, agitation, dist, comfort, detected)
```

### Animation
- Procedural gait retargeting from the player's locomotion state (limp amount, stride, posture).
- Blend layers: base idle/walk, wound overlay, breath, head-tilt/tracking.
- Mirror delay implemented as a ring buffer of player pose samples.

### Audio
- Breath layer pitched/phase-offset from the player's breath.
- Footstep echo: spawn a second footstep event `mirror_delay` after the player's, attenuated.
- Ear-injury modes: remove the echo, add detuned drone.

### Debug & telemetry (design/QA)
- On-screen overlay: PS, agitation, state, Comfort.
- Log: every CONTACT with PS, noise, the player's choices in the prior 30 seconds, and whether it was avoidable.
- Review heuristic: if >30% of CONTACTs are judged "unavoidable" in playtests, retune.

---

## 9. Playtest Questions
1. Did you notice the entity copying you? When?
2. Could you tell *why* it found you?
3. Did you ever use treatment to calm it, on purpose or by accident?
4. Did any encounter feel unfair, and what made it so?
5. Did the entity feel scary or sad, or both?

Target: players describe it as **"it wants something from me"**, not "it wants to kill me."
