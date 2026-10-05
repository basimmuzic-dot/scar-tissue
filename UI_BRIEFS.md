# SCAR TISSUE — UI Visual Briefs

*What each screen looks like and why. Principle: the interface belongs to the world. Wherever possible the player reads their body and their choices through objects in the sanatorium (hands, paper, mirrors), not floating HUD.*

**Shared visual language**
- **Typeface:** a clean, slightly worn serif (typewriter-adjacent) for documents; a thin sans for system text. No glow, no sci-fi frames.
- **Palette:** off-white paper (#E9E4D8), ink black, hospital teal (#3E6B6E) for neutral highlights, **blue-circle ink (#2F5BA8)** as the single accent that always means "yours / chosen / reached", faded grey for locked.
- **Motifs:** the scar-line (a thin white line that parts), the blue circle, a hand.
- **Motion:** slow and soft. Elements fade and draw in, never snap or slide. Audio: paper, brass, a faint hum.
- **Accessibility everywhere:** every colour state also has a shape or text state; all text scalable; screen-reader labels; reduced-motion option.

---

## 1. In-World Body Chart (the main status "screen")

**Trigger:** the player raises their hands into view, or kneels to look at a leg.

**What they see:** no menu. Mara's own hands and forearms rise into frame in the world's light. Wounds are drawn directly on the skin: a dark thread-line for a cut, a purple-yellow bruise, a swollen set of knuckles. A slow **breath-synced pulse** runs along any wound that is bleeding or unstable.

**Optional overlay (toggle, off by default):** a faint **ink sketch** of the body appears at the edge of the screen, like a margin drawing in a doctor's notebook, with six small labelled zones (hands, legs, torso, head, eyes, ears). Each zone is a small circle: empty (healthy), half-filled (treated), filled (open wound), ringed (scarred).

**Details**
- Hovering a wound in the overlay shows a one-line plain note in Mara's voice: *"Deep cut, left palm. Needs closing."*
- Scars appear as a pale line on the body and a small crescent beside the zone circle.
- Nothing pauses the game. The overlay fades out after 4 seconds.

**Must read:** where am I hurt, how badly, and what can I do about it, in under two seconds.

---

## 2. Treatment Interactions (bandage, splint)

**Look:** close on Mara's hands working on the body, lit by flashlight, steady and close. A faint **guide thread** (a thin pale line) traces the path to follow, fading as the player gets it right.

**Feedback:** no score bar. Quality is shown by the **look of the finished dressing**: tight and neat, or loose and slipping. Tremor from injuries is shown as a real shake in the hands.

**Sound:** cloth, tape, a breath held and let go.

---

## 3. Ending Cards

**Layout (1920×1080 reference)**
```
                                    [ black ]

                       ───────────────  ─ ─ ─  (scar-line draws across, parts slightly)

                        ENDING 2 OF 3
                            VESSEL

               You stayed. Nell is free. The Chorus is no longer
                  alone, and neither are you.

                       ◯   ●   ◯        ← ending tracker

                  "Some love is a place to stay."

            How this ending was reached:
            You chose to carry it. You treated 11 of 17 wounds carefully.

                                               [ Continue ]
```

**Behaviour**
1. Black, then the scar-line draws across the middle over ~2 s and parts slightly.
2. The title rises from the parting, in off-white serif, ~48pt.
3. The subtitle and closing line fade in one at a time.
4. The tracker circles fill in blue as reached; the current ending's circle **fills with a slow ink-bloom**.
5. "How this ending was reached" appears last, small.
6. Continue appears after ~6 s; it also appears immediately on any button press (never block the player).

**Per-ending tint:** Severance, a cold surgical teal edge. Vessel, a warm amber edge. Release, a pale neutral white edge. The edge tint is faint and optional (colour-blind safe, since the title text carries the meaning).

---

## 4. Post-Ending Menu

A plain page, paper background, three options as handwritten-style lines:

- **Continue** (to credits and epilogue)
- **Play another ending**
- **Main menu**

Below them, the three-circle tracker again. Selecting **Play another ending** opens Chapter Select.

---

## 5. Chapter Select / Play Another Ending

**Metaphor:** a **patient file** laid open on a desk.

**Layout:** a horizontal row of seven **index cards** (Prologue + six wards), each slightly overlapping, like paper in a folder. The currently selected card lifts and enlarges.

**Each card shows**
- Ward name and number, in serif.
- A small **painted vignette** of the ward's signature image (the shoes in the lobby, the baths' circular tubs, the theatre lamp, the ward of mirrors, the firebox, the Chorus Room dome).
- A strip of **scar marks** (small crescents) showing how many scars Mara arrives with.
- A **care fraction:** *"13 of 17 wounds treated well"* at the card where it was recorded.
- Ending tiles at the bottom: ◯ unreached, ● reached, ◌ locked with a short reason.

**Right panel (for the selected card)**
- A two-line summary of what happens in this ward.
- *"Endings reachable from here:"* with a plain list.
- A hint line when relevant: *"Release needs 70% of wounds treated well. You are at 59%. The earliest ward where it dropped: Ward 3."*
- Button: **Play from here**.

**The Chorus Room card** has a special treatment: it is drawn as the *final page*, slightly warm in tone, and is the only card that shows all three ending tiles at once.

**Spoiler setting:** when on, unreached ending tiles read "???" and their reasons are replaced with a neutral "Not yet reached".

---

## 6. Ending Gallery (post-completion)

A dim room of three framed pictures, one per ending, hung on a wall. Selecting one plays its final scene as a viewing (no play). Each frame carries the ending's card title on a small brass plaque, like the one on the Graft Beds. Unreached frames are covered by a white sheet.

---

## 7. Pause Menu

Opens as a **clipboard held by Mara**: a sheet of paper with four lines (Resume, Documents, Options, Quit), writing in a nurse's neat hand. The world behind blurs gently and the hum lowers. **Documents** opens a binder of every found item, sorted by ward, with unread ones marked by a small blue circle.

---

## 8. Documents Binder

Pages are shown as the original objects, scanned and slightly yellowed: typed memos, handwritten notes, child's drawings, a ledger page. Each page has a ribbon at the top: **ward, location, date**. Tape recordings appear as a small cassette sleeve with a **transcript** below it, always available (captions by default). Unread items carry a blue circle; read items have it hollowed.

---

## 9. Options (essentials)

Grouped on three cards: **Play**, **See & Hear**, **Comfort**.
- **Play:** Mercy Dial (labelled honestly: *"Injuries are less severe and the entity notices you from less far away"*), subtitles, control mapping.
- **See & Hear:** brightness, contrast, text size, colour-blind modes, graphic-detail reduction (injuries shown via sound and animation rather than close-ups), tinnitus-effect volume.
- **Comfort:** reduce camera sway, reduce blur, reduce flashing, spoiler setting for ending names, content notes screen.

---

## 10. Production Checklist
- [ ] Type specimens and colour tokens locked (paper, ink, teal, blue-circle, faded grey).
- [ ] Body Chart overlay, 6 zones × 4 states (healthy / treated / open / scarred).
- [ ] 7 vignettes for Chapter Select (Prologue + 6 wards).
- [ ] 3 ending cards plus the tracker animation.
- [ ] Documents Binder template for 4 item types (typed, handwritten, drawing, ledger).
- [ ] Screen-reader pass on all menus and ending cards.
- [ ] Reduced-motion variants of the scar-line and ink-bloom animations.
