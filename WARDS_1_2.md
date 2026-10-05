# SCAR TISSUE — Vertical Slice: Wards 1–2

*Target: ~35–40 min playtime. Proves three pillars: (1) a wound changes how you move and listen, (2) treatment is hands-on and risky, (3) the entity reacts to your body.*

Companion docs: `GDD.md`, `STORY.md`, `SCARS.md`, `ENTITY_SPEC.md`.

---

## 0. Slice Success Criteria
| Pillar | Pass condition (playtest) |
|---|---|
| Body as consequence | ≥80% of testers can say, unprompted, how a specific injury changed their play. |
| Diegetic treatment | Testers treat wounds without opening a menu and without being told how after the first prompt. |
| Entity reads you | ≥70% notice the entity mirroring their limp. |
| Fairness | Every injury taken is attributed by the tester to a choice or a visible hazard, not "random." |
| No soft-lock | Crawl-through route completes with any injury combination. |

---

## 1. Ward 1 — Admissions (≈12 min)

**Tone:** Quiet dread. No threat. The building is the monster.
**Mechanics introduced:** movement, flashlight, interaction, lacerations, bandaging, the in-world Body Chart (look at hands).
**Injuries possible:** Lacerations only (hands/forearms).

### 1.1 Layout (linear with loops)
```
[Entrance Hall] → [Reception] → [Records Room] ⇄ [Staff Corridor] → [Locked Stairwell (to Ward 2)]
                       ↓
                 [Waiting Room] (optional, loop-back)
```
- Entrance Hall: collapsed ceiling lets in grey daylight. Teaches "light = safety."
- Reception: desk, ledger, cracked glass partition (laceration teach).
- Records Room: filing aisles; the key beat.
- Staff Corridor: dim, long sightline, dripping.
- Stairwell door: needs a **fire-axe handle** (found in Staff Corridor) to pry, or the Records key.

### 1.2 Beat sheet
1. **Arrival.** Mara steps in from a flooded drive. Radio static. No dialogue for 60s: let the player look. Camera hands visible, holding the postcard.
2. **Postcard.** On interact, a close read: her own handwriting, a photo of a hand with a crescent scar. Mara: *"That's Nell's. That's… I drew that circle on her hand when she was nine."*
3. **Reception glass.** The partition has a gap. Reaching through is the fast path to the ledger; the safe path is the side door (needs a detour past a puddle trap). A reach through takes ~60% chance of a **hand laceration** (cues: jagged edge catches the flashlight, a visible "bite" of glass). Both routes are valid.
4. **First wound tutorial.** If cut: blood drips audibly on the floor tile. Prompt (diegetic): *Mara looks at her hand.* Raise hand into frame → Body Chart is the hand itself: wound glows faintly. If the player ignores it for 90s, a drip trail marks their path (foreshadowing the entity).
5. **Bandaging interaction (hold-and-guide):** Press and hold to press the cloth, then wrap by tracing the wound with the mouse/stick. Rushing = loose bandage (re-opens on heavy use). Slow = secure. Disinfectant is optional (raises infection risk later if skipped. Ward 5 payoff).
6. **Records Room.** The ledger shows Nell's entry: **ADMITTED 1979. GUARDIAN: M. VOSS.** Mara's signature. Environmental beat: the signature is *ink-black and fresh* on a decades-old page. (Unexplained; pays off in Ward 4.)
7. **The Quiet Moment.** The drip sound stops entirely. Ambient audio drops to a low tone for ~8 seconds. Nothing happens. *This is the slice's first scare, a sound that stops.*
8. **Stairwell.** Prying the door open produces a long metallic groan. Light from below flickers. Transition to Ward 2.

### 1.3 Scripted lines (Mara, to herself)
- Entrance: *"Eighty-one steps to the door. I counted. Habit."*
- Reception: *"Don't. Go around."* (if she reaches through) / *"Careful hands, Mara."* (if she goes around)
- Bandage: *"Steady. Over, under, tuck."* (surgical muscle memory; short, calm)
- Records: *"I signed it. I was seventeen, and I signed it."*
- Silence beat: no line.

### 1.4 Audio
- Layer 1: room tone with water drip (3D-positioned).
- Layer 2: distant structural creaks.
- Silence beat uses a hard 400ms fade to a low drone.
- Footsteps vary by surface (tile, wood, paper).

### 1.5 Teaching ladder
| Moment | Concept taught | How (no UI clutter) |
|---|---|---|
| Hall light | Light/dark | Light shafts lead forward. |
| Glass | Risk/reward | Two visible paths, one visibly hazardous. |
| Cut hand | Body Chart | Wound visible on Mara's own hand. |
| Bandage | Skill-based treatment | Hands-on action, quality matters. |
| Silence | Listening | Audio absence as cue. |

---

## 2. Ward 2 — Hydrotherapy (≈25 min)

**Tone:** Building dread; first contact.
**Mechanics introduced:** leg injuries, noise/footstep system, wading and water audio, first entity encounter, radio, splinting.
**Injuries possible:** Lacerations (hands), **leg fracture/sprain/puncture**.
**Entity:** Present from the midpoint, in *Drawn/Mirroring* states only (it never attacks in this slice's first half; see Entity Spec).

### 2.1 Layout
```
[Stair Landing] → [Locker Hall] → [Tile Baths A (shallow)] → [Catwalk Level]
                                     ↘ [Pump Room (optional)] ↗
                                       [Tile Baths B (deep)] → [Exit: Surgical Wing Lift]
```
- **Water depth zones:** dry tile (loud on debris), shallow wading (quiet, slows slightly), deep (swim, very quiet, disorienting, no flashlight beam underwater).
- **Catwalks:** rotted iron walkways above the baths, giving the high vantage point and the chase.

### 2.2 Beat sheet
1. **Landing.** Dim emergency light. Radio crackles: Tomas (first contact, see script).
2. **Locker Hall.** Rusted lockers. Searchable for supplies: bandages, a splint kit, a flare. Noise teach: broken tile crunches loudly; walking along the wall vs. through debris is a visible choice.
3. **Baths A.** Shallow pools. Player learns wading is quiet. A *wet footprint trail* leads across the floor that is **not Mara's**: it limps. (Entity seeding.)
4. **First sighting.** Across the water, a figure stands motionless, facing away. Mara's flashlight finds it, and it *turns* only when she shifts her weight. If she's uninjured, it just stands. If she has a cut hand, it raises *its* hand to match. Brief; it vanishes when the beam holds on it.
5. **Pump Room (optional).** A risk/reward side space with a medical cabinet (better supplies) but a grated floor over a drop. Taking the shortcut can cause a fall (**leg injury**); the safe route is a long loop through the baths.
6. **Catwalk set piece (see 2.3).**
7. **Baths B and exit.** Deep water crossing. Player may swim (silent, drops a carried item if hand-injured) or use a narrow ledge (loud if limping). Exit: a service lift to the Surgical Wing, needing a power switch found in the pump room or on the catwalk.
8. **Closing beat.** In the lift, the radio: Tomas says one line, then static. Mara looks at her hands. Whatever wounds she carries are drawn, in the lift's brass reflection, **on a figure standing behind her.** Fade.

### 2.3 Set Piece: The Catwalk
**Premise:** Reaching the power switch requires crossing the rotted catwalk. The Understudy, now *Approaching*, walks the baths below, mirroring Mara's movement and gait.

**Design:**
- The catwalk is ~40m with three sections: solid, rotted (visible sag, groans), and a **gap**.
- **Safe path:** Slow, crouched, on the solid girders. Silent. Takes ~90 seconds, requires reading the structure.
- **Fast path:** Run and **jump the gap** (≈55% leg injury chance, signposted by creaking audio and flaking rust).
- The entity tracks sound. A sprint across iron is loud; it moves toward the position below you.
- If Mara is already limping, the entity's gait is *also* a limp, and its footsteps echo hers a half-beat late (the "echo tell").
- **No instant death.** If the player falls, they land in the baths (water breaks the fall; take a sprain), and the Understudy is *nearby but not attacking*. The player must re-route and stay quiet.
- Success: reach the switch; the lights surge; the entity stops, head tilted, *feeling* the light.

**Possible outcomes table:**
| Player approach | Result | Consequence |
|---|---|---|
| Crouch, solid girders | Clean cross | No injury, entity loses interest |
| Run, jump gap, land | Fast, loud | 55% leg injury (limp), entity drawn |
| Run, jump gap, fail | Fall into water | Sprain; entity close, must hide/stay quiet |
| Freeze in place | Entity edges closer | Teaches stillness; non-lethal |

### 2.4 Leg-injury tutorial
When a leg wound occurs:
- **Immediate feedback:** a sharp audio sting, a half-second stumble, a limp animation begins.
- **Mechanical changes:** speed −25%, footsteps +40% loudness, no sprint-jump.
- **Treatment:** at a safe spot, the player kneels (a hold action), inspects the leg, then performs **splinting** (find straight object, bind with cloth, tighten by timing). Good splint reduces the limp to a mild one; bad splint reopens under stress.
- **Rushing** while the entity is near is possible but raises complication risk. This is a deliberate triage dilemma.

### 2.5 Scripts

**Tomas (radio, first contact, voice low and tired)**
> "…Hello? Is someone in the building? Don't answer out loud. It listens.
> You shouldn't be here. Whoever you are, there's still time. Take the road back.
> …You're not turning around. Of course you aren't.
> Listen, then. If you hear something walk like you… don't follow it. And don't let it follow you."

**Tomas (after first sighting)**
> "You saw it. I know. It does that. It's not copying you; that's what I got wrong for years.
> Keep your hands steady. That's all I can tell you."

**Tomas (lift, final line)**
> "Whatever you've got on you, wounds, I mean… don't leave them open. It can tell."

**Mara (internal, sparse)**
- Seeing the figure: *"Don't run. Don't…"*
- After splinting: *"Setting a bone in a bathhouse. Fine."*
- On the catwalk, if she leaps: *"That's… not far."* (self-bargaining; adds guilt echo)

**Found documents (optional, Ward 2)**
- **Hydrotherapy log, 1961:** *"Patient 14 reports 'the cold feels shared.' Dr. H. notes this is the therapy working."*
- **Nurse note:** *"They stopped screaming in the baths. Not because the pain stopped. Because it stopped being theirs alone."*

### 2.6 Audio and Lighting for Ward 2
- Water carries sound *further* than air. The slice teaches this by letting the player hear the entity's steps from far off while in water.
- Lighting: flashlight is key. Underwater has no beam. Emergency lights flicker in time with the entity's proximity.
- Entity audio: breath doubled with the player's breath, offset by a fraction. Ear injuries (not in this slice) will break this tell.

---

## 3. Asset List (Vertical Slice)
**Environments (modular):** hospital tile set, plaster/paint decay set, iron catwalk kit, water volumes with depth shader, locker/cabinet props, a stairwell, lift.
**Characters:** Mara first-person hands and legs with wound variants (laceration ×3, leg: sprain, fracture, puncture); the Understudy mesh with procedural gait mirroring.
**Props/interactables:** bandages, splint, disinfectant, flashlight, flare, ledger, postcard, radio.
**Audio:** surface-dependent footsteps ×6, water states ×3, entity breath layer, radio VO, drone/silence transitions.

## 4. Milestones
1. Greybox Ward 1 + bandaging interaction.
2. Greybox Ward 2 + noise/footstep system + catwalk.
3. Entity mirroring prototype (Drawn/Mirroring).
4. Art/audio pass + playtest against section 0 criteria.
