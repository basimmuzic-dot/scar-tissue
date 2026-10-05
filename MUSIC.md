# SCAR TISSUE — Music Design

*The score is sparse by design. Silence and the Chorus's hum carry most of the dread. Music enters only to mark a human feeling, never to announce a scare.*

---

## 1. Principles
1. **Music = feeling, not warning.** Never cue danger with a stinger. If the entity is near, the *sound design* tells the player.
2. **Few instruments, played close.** Intimacy over scale. Everything should sound like it is in the next room.
3. **One idea, returning.** The score is built from two seeds: the **four-note piano motif** (Mara's guilt and love) and the **Chorus drone** (the shared hum).
4. **Silence is an instrument.** Whole wards play with no music at all.
5. **Diegetic where possible.** A music box, a hummed lullaby, a cassette, an old piano in the Waiting Room. The score grows out of sounds in the world.

---

## 2. Palette (Instrumentation)
| Element | Use |
|---|---|
| **Felt-muted upright piano** | The four-note motif. Soft, close, slightly out of tune. |
| **Solo cello / bowed vibraphone** | Warmth, grief; Mara's emotional lines. |
| **Voices (ensemble hum, sung vowels)** | The Chorus. Wordless, unified pitch, in-engine layered. |
| **Glass harmonica / bowed glass / singing bowl** | The baths, the mirrors, the sense of water. |
| **Music box** | The memory of childhood; the Nell theme. |
| **Low sustained drone (analog synth or organ pedal)** | The building's pitch (see §4). |
| **Prepared piano & tape loops** | Texture for the Surgical Wing and Henn. |

**Avoid:** big orchestra, percussion hits, risers, brass.

---

## 3. The Four Motifs

### A. Mara's Motif (4 descending piano notes)
A short falling figure: *3 – 2 – 1 – 5̣* (a gentle descent that resolves *down*, never home). First heard on the photograph in the opening. Returns whenever Mara thinks of Nell, and in every ending, played slower each time.
- **Variation:** in the Release ending, the fourth note finally **resolves upward** to the tonic.

### B. The Chorus Drone
A single sustained pitch (**D**) hummed by a layered ensemble. This is the "building's pitch." Everything else tunes around it.
- Grows from barely audible (Ward 1) to full chord (Chorus Room).
- **In the endings:** Severance, the drone *fades by one voice at a time*. Vessel, it settles into a warm sustained chord. Release, it opens into a major third and ends.

### C. The Nell Theme (music box)
A simple lullaby-like melody in 3/4, 8 bars, slightly off-pitch like a worn comb. Appears diegetically (a music box in the Waiting Room, a hummed line in Nell's tapes) and later in the Chorus's voices, **harmonised**, when the player is close to Nell.

### D. Henn's Theme (prepared piano + tape)
A slow, formal hymn-like phrase in the piano's lowest register, with a slight tape-warp. Warm, then increasingly strange. Heard in the Surgical Wing, in the recordings, and quietly in the Chorus Room (his presence).

---

## 4. Harmonic World
- **Home pitch:** D (the Chorus drone). Mara's motif sits in D minor.
- **Water/Baths:** open fifths (D–A) with glass harmonics.
- **Surgical Wing:** minor second clusters, quiet and tight.
- **Mirror Ward:** the Nell theme in D major, tender but wavering.
- **Boiler House:** low drones, detuned organ; rhythm from the fire, not drums.
- **Foundations:** all voices in unison, then slowly opening into chords.

---

## 5. Cue List by Ward

| Ward / Moment | Music | Notes |
|---|---|---|
| **Cold open (1979)** | None; a faint music box under the kitchen scene | Warm, nostalgic, then cut |
| **The drive (1994)** | Piano motif once, when Mara looks at the photograph | Soft, single statement |
| **Title** | Chorus drone resolving to a chord, then silence, then bell | See cinematic doc |
| **Ward 1** | **No score.** Room tone and the drip only. | Silence beat is the "music" |
| **Ward 2** | Glass harmonica swells when the player first sees the baths. The Understudy has *no* theme. | Beauty first |
| **Catwalk** | Only the drone rising and a tight pulse from the metal itself | No rhythm, no drums |
| **Ward 3** | Henn's Theme in the theatre; prepared piano in the corridors | Cold and formal |
| **Henn's tapes** | The tape *is* the music (Henn's voice, light piano) | No score on top |
| **Ward 4** | Nell's music box; the drone rises softly when she speaks | The most tender cue |
| **Understudy offers its hand** | Mara's motif on solo cello + piano; drone drops to one voice | The emotional peak |
| **Ward 5** | Low organ and the sound of the furnace; one cello line during Tomas's confession | Human warmth in heat |
| **Collapse** | Strings of struck metal, not orchestral; no melody | Chaos is sound, not score |
| **Ward 6 descent** | Chorus drone builds, voices enter one by one | Awe |
| **Nell's first words** | Everything stops. Only her voice and the drone. | Silence before the question |
| **Ending A: Severance** | Voices drop out one by one, leaving cello and piano | Loss with relief |
| **Ending B: Vessel** | Warm sustained chord from all voices, slow music-box pulse | Peace |
| **Ending C: Release** | Mara's motif resolves upward; chorus opens to a major third | Release |
| **Epilogue** | Music-box theme alone | Gentle |
| **Credits** | Piano suite of all four motifs, slow, then silence | |

---

## 6. Interactive Music System
- **Layers, not tracks.** Each ward has a bed (drone) plus optional layers (cello, glass, piano) that fade in/out with *story state*, not combat state.
- **Triggers:** story moments, found documents, proximity to Nell-related objects. **Not** proximity to the Understudy.
- **Silence rule:** in any ward, the system holds at least **60% of play time music-free**.
- **Injury link (subtle):** serious injuries slightly detune the drone, and hearing damage filters the music in the same way as everything else (low-pass, tinnitus tone).
- **Care link:** well-treated wounds nudge the drone toward consonance; neglect toward dissonance. The player never sees it, but feels it.

---

## 7. Production Notes
- **Composer brief:** a composer comfortable with restraint: acoustic, chamber, voice, and sound-art. Reference mood: intimate chamber music meeting field recordings, not trailer music.
- **Recordings:** felt piano in a dry room; cello in a stairwell for natural reverb; the choir recorded close and in a stone space; the music box on real mechanism.
- **Stems:** deliver separate stems (piano, cello, voices, glass, drone, texture) for the interactive system.
- **Deliverables:** ~45 minutes of finished music (about 20 minutes interactive layers, 25 minutes linear cues), plus ~30 minutes of loopable beds and 60 stingers-that-are-not-stingers (soft story markers).
