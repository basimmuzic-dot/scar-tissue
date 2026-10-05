# SCAR TISSUE — Ending Presentation & Checkpoint System

*Design decision: the game always tells the player which ending they reached, and always lets them return to see the others. An ending's image may stay poetic. Its identity is never left for the player to guess.*

Supersedes the "left open on purpose" note on the Vessel ending in `WARDS_3_6_SCRIPTS.md`. The final image (the raised hand in the window) stays, and the ending card below names what it means.

---

## 1. Ending Cards

After each ending's final scene and before the epilogue postcard, a full-screen card holds for ~6 seconds on a black ground with the scar-line motif from the title sequence.

| Ending | Card title | Subtitle (what it was) | Closing line |
|---|---|---|---|
| Severance | **ENDING 1 OF 3: SEVERANCE** | *You cut the thread. Nell is free. You carry what she carried.* | "Some healing is a trade." |
| Vessel | **ENDING 2 OF 3: VESSEL** | *You stayed. Nell is free. The Chorus is no longer alone, and neither are you.* | "Some love is a place to stay." |
| Release | **ENDING 3 OF 3: RELEASE** | *You carried it together, and set it down. Nobody was left behind.* | "Some pain only needs to be heard." |

**Rules**
- The card states **what happened to Mara and to Nell** in plain words. For Vessel that means the card says Mara remains in the building, so the window image is understood as her.
- The card shows the **ending tracker**: three small circles (the blue-circle motif), filled for each ending the player has reached on this profile.
- The card shows a one-line **"How this ending was reached"**, derived from the player's history (e.g., *"You treated 14 of 17 wounds carefully."*). This teaches the player what shaped the result without a lecture.
- After the epilogue postcard, the player sees a menu: **Continue / Play another ending / Main menu**.

---

## 2. Play Another Ending (Checkpoints)

### 2.1 What is saved
The game keeps **two kinds of checkpoint**, both created automatically:

1. **Ward checkpoints:** one at the start of each of the six wards, plus the cinematic. Each stores the full **body state** (wounds, scars), inventory, found documents, and the silent **treatment-philosophy tracker** (see §3).
2. **The Threshold checkpoint:** created the moment Mara enters the Chorus Room, just before Nell's question. This is the main route to the other endings.

Checkpoints are listed on a **Chapter Select** screen, showing the ward name, a small painting of its signature image, the scars Mara carried in, and which endings are reachable from here.

### 2.2 Playing another ending
From the post-ending menu, or the Chapter Select screen, **Play another ending** shows the three endings as tiles:

| State | Display |
|---|---|
| Reached | Tile filled, ending card thumbnail. |
| Available from the Threshold | Tile lit, with a "Replay from the Chorus Room" button. |
| Not yet available from the Threshold | Tile dimmed, with a plain explanation of what is missing and a button to **choose a ward to replay from**. |

### 2.3 How each ending is unlocked
- **Severance (Operate):** always available from the Threshold. It needs a surgical action, not a prior history.
- **Vessel (Stay):** always available from the Threshold. It needs only the player's choice.
- **Release (Let go):** requires the **Compassion threshold** from the whole run (see §3). If the Threshold checkpoint doesn't meet it, the tile reads:
  > *"The Chorus does not trust you yet. Release is earned by how you cared for wounds, yours and others', before you arrived."*
  and offers **Replay from a ward** with a suggestion of the earliest ward where the player's care dropped below the threshold, e.g., *"Ward 3: you left 4 wounds untreated."*

Replaying from an earlier ward starts that ward's checkpoint with the stored body state, so the player continues the same story with a better chance to change what matters.

### 2.4 Optional cheat-free convenience
- **Ending Select unlock (after all three endings are reached):** a hidden **"Gallery"** lists the three ending scenes for viewing without play.
- **New Game+** (scars carried over) is unlocked after the first ending of any kind.

---

## 3. Compassion Tracker (visible rules, not hidden)

The tracker used by Release is already in the entity spec as "Care Resonance." Make its logic **readable**:

- **What counts:** wounds treated cleanly (bandaged or splinted without a failed attempt), wounds treated while the Understudy is nearby, rescuing Tomas, and moments of stillness near the Understudy that settled it.
- **What doesn't:** rushing treatment, leaving wounds open to complication, fleeing past the Understudy while it was calm.
- **Threshold:** at least **70%** of wounds treated well *and* at least one SOOTHED encounter in Wards 2–4. **Fairer alternative:** at least **50%** *and* completing the **Bedside Care** sequence in the Chorus Room (treating the Chorus's own wounds with remaining supplies), which adds directly to the score. The Chorus Room itself teaches the idea (Nell: *"They only want to be held"*), so no earlier tape is required.
- **Visibility:** the Chapter Select screen shows the current score as a **plain fraction** ("13 of 17 wounds treated well"), never as a hidden meter. Players should know where they stand.

This keeps the system fair: nobody misses the best ending without a way to find out why and fix it.

---

## 4. Interaction With Other Systems

- **Scars** on checkpoint load are restored exactly. Players cannot "heal" a checkpoint into a better state, only play on from it.
- **Fail state:** the existing "wake in the last safe room" rule stays. Checkpoints are for choosing endings, not for undoing failure.
- **Found documents:** carried over. Replays do not require re-reading anything, but unseen documents are flagged so players can finish collecting them.
- **Accessibility:** the ending cards are read aloud when screen-reader support is enabled, and the tracker uses both shape and colour.
- **Spoiler setting:** a toggle in options hides ending names on the Chapter Select screen until reached, for players who want to discover them cold. It defaults to **off**, since the stated intent is clarity.

---

## 5. Why This Is the Right Call
- **Clarity respects the player.** A strong ending should be understood before it is debated. Poetic imagery lands better once the player knows what they are looking at.
- **Replay becomes a choice, not a grind.** Checkpoints at the Threshold let a player see Severance and Vessel in minutes. Release, which depends on how they played, gets a clear path to be earned.
- **It keeps the ending's meaning with the author.** Naming the ending removes accidental misreadings without flattening the story.
- **The cost is small.** Six ward checkpoints, one Threshold checkpoint, and one Chapter Select screen reuse the existing save data.
