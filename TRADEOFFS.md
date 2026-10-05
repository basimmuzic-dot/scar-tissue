# SCAR TISSUE — Trade-offs & Hard Decisions

*Audit of whether the design forces real dilemmas, and the changes that make it do so.*

## 1. Honest Audit of the Previous Design

The question: does the player ever have to choose between two things that both matter, where each choice gives something and costs something?

**What existed:** treat slowly (clean heal) vs. rush (complication risk); take risky shortcuts for speed; triage when the entity is near.

**The weakness:** these were mostly *one-sided*.
1. **Slow treatment had almost no cost.** In a safe room, taking your time was free. The only price was time near the entity, so the optimal play was "treat everything carefully, always."
2. **Ignoring a wound had almost no upside.** It only added risk. A rational player never ignored anything.
3. **Supplies were "always sufficient."** With no scarcity, nothing competed with anything else.
4. **Only one safe room per ward** meant most treatments happened in the safe room anyway, which made the one real trade-off (treat now vs. later) rarely bite.

**Verdict:** the dilemma existed in the text but not in the economics. The fixes below give treatment and neglect each a real price and a real reward.

---

## 2. The Principle

> **Every decision about the body spends something the player also needs elsewhere.**

Four things compete. Each treatment choice trades one against another, and no choice wins on all four.

| Resource | What it is | Spent by | Gained by |
|---|---|---|---|
| **Supplies** | Bandages, splints, disinfectant, sutures | Careful treatment | Exploring, risky side rooms |
| **Time & Noise** | Seconds spent kneeling, noise made | Careful treatment | Skipping treatment |
| **Mobility & Dexterity** | Speed, climbing, fine-motor tasks | Some treatments (a splint stiffens a leg; a tight dressing stiffens a hand) | Leaving the wound loose or untreated |
| **The Entity's attention** | Pain Signature, agitation | Untreated wounds (they attract it) | Treating wounds (calms it) *or* using open wounds as a lure |

---

## 3. Changes That Create Real Dilemmas

### 3.1 Scarcity: supplies are enough to survive, not to be perfect
- Supplies cover **roughly 12 of the ~17 wounds** an average player takes. Careful play can treat most wounds; nobody treats all of them properly.
- This matches the Release threshold (70%), so Release asks for *mostly* careful, never *perfectly* careful.
- **Fairness guard:** a basic improvised option (cloth strip, broken pole) always exists. It heals poorly but never softlocks.

### 3.2 Treatment has a body cost, not just a time cost
| Treatment | Benefit | Cost |
|---|---|---|
| **Tight bandage (hand)** | Clean heal, no scar | Fine-motor tasks (locks, surgery, writing) are harder for ~2 minutes |
| **Quick wrap (hand)** | Stops bleeding now, hands stay free | May re-open under strain; risk of Pale Seam scar |
| **Full splint (leg)** | Reduces limp, prevents Old Break | **Cannot vault or crouch-sprint** while splinted (~2 min); kneeling takes ~60 s and is noisy |
| **Tourniquet (any limb)** | Stops serious bleeding instantly | Risk of **Pressure Mark** scar; limb numb (reduced control) |
| **Disinfectant** | Avoids later infection | Uses a scarce item; stings (brief tremor) |

### 3.3 Ignoring or rushing a wound has real upsides
| Choice | Upside | Downside |
|---|---|---|
| **Leave a leg wound unsplinted** | Keep full mobility to vault, climb, and sprint-jump *now* | Limp worsens; footsteps stay loud; risk of Old Break |
| **Quick wrap, skip disinfectant** | Saves the scarce item for a worse wound | Infection risk in Ward 5 |
| **Keep bleeding on purpose (bait)** | Your Pain Signature draws the Understudy toward the blood, **away from a route you need to cross** | The longer you wait, the more the wound worsens; it may follow the trail back to you |
| **Take a wound to save time** | Skip a slow route | The wound becomes a scar and a permanent modifier |

### 3.4 Care competes with other goals
The three endings reward different, partly conflicting play:

| Ending | Rewards | Conflicts with |
|---|---|---|
| **Release** | Careful, compassionate treatment across the game (≥70%) | Speed; risky shortcuts; the supplies needed for a Hard Surgery |
| **Severance** | Surgical skill (Hard Surgery challenges, Surgeon's Callus) | Hard Surgery uses supplies and leaves hands injured for a while, which can lower `CARE` |
| **Vessel** | A body that has *borne* a lot (the Chorus Note scar at 6+ scars adds a stronger bond) | Treatment that prevents scars |

A player cannot maximise all three. They choose which kind of doctor to be.

---

## 4. The Dilemma Catalogue (by ward)

Each dilemma has two options that are both defensible.

### Ward 1: Admissions
- **Glass partition.** *Reach through* (fast, 60% hand cut) vs. *side door* (slow, safe).
- **First cut.** *Tight bandage* (clean, but stiff hands for 2 min while the silence beat plays) vs. *quick wrap* (hands free to explore, might re-open).

### Ward 2: The Baths
- **Splint now vs. cross now.** A broken leg *before* the catwalk: splint (60 s, noisy, **can't vault the gap**) vs. push on limping (fast, loud, can vault, entity drawn).
- **Pump Room cabinet.** Extra supplies, but the shortcut grating can cost a leg. Take the supplies *and* the risk, or skip both.
- **Bait.** A bleeding player can lure the Understudy to the grating while they cross the catwalk, but the wound worsens while they wait.

### Ward 3: The Surgical Wing
- **Extended treatment in the theatre.** Heals everything properly but takes ~4 minutes of play, during which the player is *not* progressing or finding documents.
- **Hard Surgery challenge (optional).** Earn a permanent upside (Surgeon's Callus) but spend several supplies and leave the hands injured (tremor) for a ward.
- **Tapes.** Listening takes time and keeps the player in the office with open wounds.

### Ward 4: The Mirror Ward
- **Meeting the Understudy.** *Stay still, wounded,* to be soothed (+`SOOTHED`) vs. *treat first* (cleaner body, but moving and kneeling near it can unsettle it).
- **Reading the mirrors.** Scanning slowly reveals a safer path but delays treatment.

### Ward 5: The Boiler House
- **Rescue Tomas** (serious injury, large supply cost, `CARE +`, ally) vs. **press on** (body and supplies kept, lose Tomas).
- **Infection.** If the player skipped disinfectant, they must now spend remaining supplies on an infected wound or push on feverish (blur, tremor).

### Ward 6: The Foundations
- **Bedside Care vs. surgical prep.** Spend remaining supplies treating the Chorus's pain (Release path) or keep them for the surgery (Severance path).
- **Taking on pain.** Vessel asks the player to *accept* wounds the Chorus has been carrying, directly opposed to treating them.

---

## 5. Rules That Keep the Dilemmas Fair

1. **Every option is viable.** No choice is a trap; each leads to a playable, finishable game.
2. **Every cost is visible before the choice.** Icons or Mara's line state what a choice will cost (*"This will keep me from vaulting."*).
3. **No hidden rubber-banding.** The player is never silently rescued from a bad trade.
4. **Trade-offs are about *kinds* of value, not good vs. bad.** Neither speed nor care is "wrong"; they are different.
5. **Safe rooms are sparse (one per ward).** Most wounds happen far from one, which makes "treat now vs. later" genuinely tense.
6. **Improvised options always exist.** Scarcity never softlocks.
7. **Consequences are readable.** The Body Chart and Chapter Select show exactly why a result happened.

---

## 6. QA Tests for the Trade-offs
- **No dominant strategy:** across test runs, no single policy (*always treat slowly*, *never treat*, *always rush*) should reach the best outcome on all of: survival ease, Release, Severance, Vessel and speed.
- **Dilemma frequency:** a typical ward should present 3–5 distinct trade-offs.
- **Scarcity calibration:** an expert player should finish with 0–2 spare supply units; a careless player should run out by Ward 5.
- **Playtest question:** *"Was there a moment you wanted to do two things and couldn't?"* Target: ≥80% say yes, and describe it as *interesting* rather than unfair.

---

## 7. Changes to Other Documents (applied)
- **GDD:** supplies line updated from "always enough" to "enough to survive, not to be perfect."
- **Playthrough:** failure path updated; Release and Severance fairness changes applied (see §8).
- **Endings doc:** Release threshold made fairer (see §8).

---

## 8. Fairness Fixes Applied Alongside This Audit

### 8.1 Release is now fairer
Problem: Release depended on having heard Henn's "please be gentle", and a player at 59% care had no way to recover except replaying whole wards.

Fixes:
- **The Chorus Room now teaches the idea itself.** Nell says it in plain words (*"They only want to be held. Dr. Henn used to say: be gentle."*), so no earlier tape is required.
- **Bedside Care sequence.** In the Chorus Room, the player can treat the Chorus's own wounds (frayed cords, burned patches) with whatever supplies they still have. Completing it **adds directly to `CARE`**.
- **Revised threshold:** Release unlocks if **`CARE ≥ 70%`**, **or** **`CARE ≥ 50%` and Bedside Care is completed**. Players near the line can still earn it in the final room.
- **Clear hints.** The Chapter Select screen and the ending card say exactly what to try.

### 8.2 Severance surgery is fairer
Problem: a failed surgery with shaky hands could feel punishing for a player who hadn't built up skill.
Fixes:
- A failed attempt **stabilises** the cord rather than ending the run, and the player may retry immediately with no penalty.
- A **steadying aid** (resting the elbows on the platform) is always available as a compensation technique, so no player is locked out of Severance by their scars.
- If the player's hands are injured, Mara notes it (*"My hands aren't steady. Brace the elbow."*), pointing to the aid.
