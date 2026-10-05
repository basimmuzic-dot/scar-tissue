# SCAR TISSUE — Sound Design

*In this game sound is the primary sense. The player's ears are as vulnerable as their hands, and the entity is heard long before it is seen. Binaural 3D audio is mandatory.*

---

## 1. Pillars
1. **Sound is information.** Every important thing is audible: the entity, wounds, water, structure.
2. **The ear is a body part.** Ear injuries change the mix itself, not just a filter on top.
3. **Silence is a event.** A sudden absence is the strongest cue in the game.
4. **The building breathes.** Constant low life (creaks, drips, hum) makes the quiet legible.
5. **Everything handled sounds handled.** Surfaces, cloth, paper and metal carry the history of touch.

---

## 2. Spatial Audio & Mix
- **Format:** binaural headphone mix as the reference; stereo speaker and surround as scaled-down variants.
- **Reverb:** per-room impulse responses recorded or modelled: marble lobby (long, bright), tiled baths (very long, glassy), brick boiler hall (dark, short), stone vaults (wet, enveloping), carpeted offices (dry).
- **Propagation:** sound passes through doors and walls with correct occlusion and low-pass. **Water carries sound further** (see §4).
- **Priority mix:** (1) dialogue and story audio, (2) entity and threat cues, (3) the player's body and actions, (4) ambience, (5) music.
- **Loudness:** target quiet baseline with real dynamic range. Peak moments reach, but do not exceed, a controlled ceiling. No hearing-damaging spikes.

---

## 3. The Player's Body (Foley & Biosound)

### Breath and heartbeat
- Continuous low breath, scaling with stamina, fear and injury. Heartbeat appears only under high stress, and **never** as a "danger meter".
- When hiding with a torso injury, breath becomes audible and must be managed (Shallow Breath technique).

### Footsteps
- 8 surfaces: marble, tile, wood, wet tile, shallow water, deep water, soot/coal, stone.
- **Injury layers:** a limp adds an uneven second tone; a splint adds a faint creak of binding; a broken tile or debris adds brittle crunch.
- Weight-shift and heel-toe techniques change footstep timbre audibly, so players *hear* their adaptation working.

### Wounds & treatment
- **Bleeding:** slow drips with real surface response (tile ping, water plop, cloth patter).
- **Bandaging:** cloth, tape, a small exhale. Quality shows in sound: tight wrap squeaks softly, loose wrap rustles.
- **Splinting:** wood, binding, the player's breath held for the tightening.
- **Pain:** recorded vocalisations (see Voice Casting §1) scaled by severity; **never used as a jump-scare**.

### Ear injuries (sound as the system)
| State | Effect |
|---|---|
| **Tinnitus** | A faint, slowly cycling tone masking quiet cues; listening "between" the cycles is the compensation. |
| **Hearing loss (one side)** | That side dampened (low-pass, level cut). Directional cues skew toward the good ear. |
| **Concussion** | Brief muffled thump and dulling of high frequencies after impact, recovering over seconds. |
- All ear effects have **accessibility sliders** and a **non-audio fallback** (e.g., ripple cues in water).

---

## 4. The Building (Ambience & Environment)

### Constant layers
- **Room tone:** a different hum per ward (see §5).
- **Water:** the sound of drips, flow, and sloshing; always positioned in 3D.
- **Structure:** creaks, settlings, wind in the ducts; tied to weather and the building's "mood".
- **The Hum:** the Chorus's drone, present in every ward at a level that rises with proximity to Nell. At low volume it should read as ventilation, until the player realises it is voices.

### Water physics (core to stealth)
- Shallow water: soft, **quiet** wading; splashes only on quick moves.
- Deep water: sound dulls, muffled underwater mix, heartbeat and breath dominate.
- **Water carries sound farther**; an entity's steps and the Chorus's whispers are heard from further away in wet areas. A player who learns this can use it.

### Weather
- Constant rain on roofs, distant thunder only at story beats. Rain intensity varies by floor; none in the foundations.

---

## 5. Ward Soundscapes

| Ward | Room tone | Signature sounds | The "tell" |
|---|---|---|---|
| **Approach** | Rain on leaves and a car engine ticking | Wipers, mud underfoot, gate hinges | The building goes quiet as the doors open |
| **1: Admissions** | Marble hush, slow drip into a pail | Paper rustle, distant creak, chandelier chain | **The drip stops** (the silence beat) |
| **2: Baths** | Long wet reverb, pipes weeping | Lockers clanging, water slap on tile, amber emergency lamp buzz | Echo footsteps a half-beat late |
| **3: Surgical** | Dry, chemical hush, electrical buzz | Instruments clinking, tape hiss from Henn's tapes, caged-bulb hum | The chair creaking when nobody is there |
| **4: Mirror Ward** | Soft rain, high windows, faint voices | Mirrors "singing" faintly when touched, child's tape hiss | The Chorus's hum rising when Nell speaks |
| **5: Boiler** | Roar of low flame, hot metal ticking | Coal shifting, steel expansion groans, a radio's static | The furnace sounds like breathing |
| **6: Foundations** | Warm, wet, enveloping | Cord pulses (heartbeat-tied), water answering steps, distant faces whispering | Ripples return the player's steps a moment late |

---

## 6. The Understudy (Audio Character)

The most important sound design in the game. It is never given growls, roars or stings.

- **Breath:** doubles the player's own, offset by a fraction. This makes it feel like an echo of the player.
- **Footsteps:** echo the player's footsteps ~0.4 s later, attenuated; matches the limp when the player is limping.
- **Proximity:** the doubled breath gets closer, warmer, more present. It never becomes louder than the player's own.
- **States (audio):**
  - Dormant: faint held breath in the distance.
  - Drawn: small steps, pauses, tilted-head rustle.
  - Mirroring: full echo of footsteps and breath.
  - Approaching: breath ragged, doubled tone lowers.
  - Contact: a 1.2 s swell of a low tone before an attack.
  - Soothed: breath slows, steps fade, soft exhale.
- **Ear-injury break:** with hearing loss, the echo tell disappears, forcing the player to rely on visual cues. This must be audible as a loss, not a bug.

---

## 7. The Chorus (Audio Character)
- **The hum:** one pitch, 12–20 voices, close-miked, slow breathing in and out.
- **Whispers:** word fragments surfacing from the hum (*Hello. You hurt.*).
- **In the Chorus Room:** voices are placed all around, including above (the dome) and below (the water). The whole room should feel like being *inside* a body.
- **Scar notes:** each of the player's scars adds a distinct soft tone to the Chorus's chord, so the player hears their own history sung back.

---

## 8. Interface Sound
- Soft, paper- and cloth-based. No beeps or digital blips.
- **Menu:** the turn of a page, a pencil tick.
- **Documents:** paper unfolding; cassette inserted for tapes.
- **Ending cards:** a single bell on the title; ink-bloom has a very soft water-drop.
- **Chapter Select:** index cards sliding over each other, light wood.

---

## 9. Key Moments (Sound Direction)

| Moment | Direction |
|---|---|
| **The silence beat (Ward 1)** | Hard 400 ms fade of drip and room tone to a low drone, held 8 s, then return. |
| **First sighting (Ward 2)** | The Understudy's breath appears *inside* the player's own, so the player thinks it's theirs, then realises it's not. |
| **Catwalk** | Iron groans as part of the music; no melody. The Understudy's echo steps are below, unseen. |
| **Mirror Ward reveal** | Nell's present-day voice enters over the tape, perfectly in sync with her child voice. |
| **The open hand** | Everything drops to the player's heartbeat and the drone, then the cello. |
| **Boiler collapse** | Metal, wood, and water in three distinct layers; Tomas's voice stays dry and clear. |
| **Chorus Room** | The whole mix resolves to one chord; Nell's voice sits at its centre. |

---

## 10. Tools & Production
- **Middleware:** a game audio engine with object-based spatialisation, real-time occlusion/obstruction, convolution reverb and a state-driven music system.
- **Field recording list:** a decommissioned hospital or school (real room tones), a boiler house, a swimming bath (tiled reverbs), a stairwell (cello), stone cellar, rain at night, tape machines, brass lift, music box.
- **Procedural audio:** footstep layers driven by gait data; breath doubling for the Understudy; wounds' effect on mix.
- **Testing:** test everything on headphones, small speakers and with hearing-loss simulation. Test the ear-injury mix with players who have real hearing differences.

## 11. Accessibility Summary
- Full captions with sound descriptions (*[drip stops]*, *[Chorus hum rises]*).
- **Visual sound cues:** optional on-screen markers or ripples for the Understudy's direction and distance.
- **Sliders:** master, dialogue, music, effects, tinnitus-effect level, hearing-loss-effect level.
- **Mono mode** and **balance control** for single-sided hearing.
- **Dialogue boost** and **dynamic range** (night mode) options.
- No flashing audio-visual coupling; no sudden loud events without a preceding cue.
