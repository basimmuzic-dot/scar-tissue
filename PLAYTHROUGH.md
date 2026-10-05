# SCAR TISSUE — Branching Playthrough (Played by Speech)

*A narrated run of the whole game: the player does X, the game does Y, and at each fork it says what happens if the player does one thing or the other. Use it as a test script, a QA path list, and a design check that every choice has a visible consequence.*

**Notation**
- **PLAYER:** an input or decision. **GAME:** what the world does back.
- **IF / ELSE:** a branch. **[STATE]** marks something stored (a wound, a scar, a counter).
- **Counters tracked silently, shown only on Chapter Select:** `CARE` (wounds treated well ÷ total wounds), `SOOTHED` (calm encounters with the Understudy), `TOMAS` (rescued / left), `SCARS`.
- Controls named generically: **Move, Look, Interact (hold), Raise Hands, Crouch, Sprint, Flashlight, Listen**.

---

## PROLOGUE: Cinematic

1. **GAME:** 1979 kitchen. Young Mara signs forms; draws a blue circle on Nell's hand. Cut to 1994, Mara driving with the postcard. Her car stalls in the flood. Title card.
2. **PLAYER:** (no control) **GAME:** hands control at the open doors. A prompt: *Hold Interact to open the door.*

---

## WARD 1: ADMISSIONS

### 1. Entrance Hall
3. **PLAYER:** walks in, looks around. **GAME:** shaft of daylight, shoes, toppled wheelchair. No threat.
4. **PLAYER:** picks up the postcard from Mara's pocket (Interact on hands). **GAME:** close read of the handwriting and Nell's scar. Mara line: *"That's Nell's."*
   - IF the player reads it fully, THEN Mara says the second line about drawing the circle. ELSE (they skip), the line plays later in the Records Room.

### 2. Reception: the first choice
5. **PLAYER:** goes to the reception desk. **GAME:** a gap in the glass partition shows the ledger.
   - **IF the player reaches through the gap** → 60% chance **[WOUND: hand laceration]**. Glass bites; blood drips.
     - **IF cut** → the drip is audible. A dim prompt: *look at your hand.* PLAYER raises hands → wound glows.
       - **IF the player bandages** (hold Interact, trace the wound):
         - IF done slowly and fully → **clean heal**, `CARE +1`.
         - IF done fast/sloppy → loose bandage; it re-opens under heavy use; small `CARE` credit only.
       - **IF the player ignores it for 90 s** → a drip trail follows them (foreshadows the entity). After a longer window it becomes **[SCAR: Pale Seam]**.
     - **IF not cut (40%)** → ledger reached, no wound.
   - **ELSE the player takes the side door** (a longer loop past a puddle trap) → no wound risk, ledger reached. Mara: *"Careful hands, Mara."*

6. **PLAYER:** reads the ledger. **GAME:** *VOSS, NELL. 14 Mar 1979. Guardian: M. VOSS.* Signature in wet-looking ink. Mara: *"I signed it. I was seventeen."* **[SCAR: Signature Scar]** appears as a crescent mark on her hand (story, no penalty).

### 3. Records Room
7. **PLAYER:** enters the Records Room. **GAME:** one aisle is tidy, narrow footprints lead in and none lead out. The drawer marked **V** is open, an empty folder inside.
   - IF the player follows the footprints → they end at a wall; the dust has a clean handprint. (A small hint of Nell's hiding places.)
   - ELSE (skips) → nothing lost; the footprint motif repeats in Ward 2.

8. **PLAYER:** collects an axe handle in the Staff Corridor. **GAME:** the dispensary and linen doors are searchable. The "Administrator" door is locked.
   - IF the player searches dispensary → finds **bandages** and **disinfectant**.
     - IF they take disinfectant and use it on a wound later → infection risk drops.
     - ELSE skip → infection risk rises for open wounds [Ward 5 payoff].

### 4. The Silence Beat
9. **PLAYER:** walks down the corridor. **GAME:** the drip stops. Drone. 8 seconds of silence. Nothing happens.
   - IF the player freezes or listens → the quiet lasts the full 8 s.
   - ELSE (keeps walking) → the silence still plays, but their footsteps feel unnaturally loud.

10. **PLAYER:** pries the stairwell door with the axe handle (hold Interact). **GAME:** a long groan, blue-white light from below. **Ward 2.**

---

## WARD 2: THE BATHS

### 1. Landing and radio
11. **PLAYER:** descends. **GAME:** amber emergency lights. Radio crackle: **Tomas's first call** (*"Don't answer out loud. It listens."*).
    - IF the player says nothing / doesn't use the radio → Tomas finishes anyway; nothing is lost.

### 2. Locker Hall
12. **PLAYER:** searches lockers. **GAME:** finds a **splint kit**, a flare, extra bandages.
    - IF the player takes the splint kit → leg injuries later are treatable at full quality.
    - ELSE skip → they must improvise with a broken pole (lower quality).
13. **PLAYER:** notices **small bare wet footprints** crossing the floor. **GAME:** they lead into the baths.

### 3. Baths A
14. **PLAYER:** wades into shallow water. **GAME:** wading is quiet. A *second* set of footprints appears that limps.
    - IF the player has a hand wound → the limping prints now show a **hand-print** on the wall beside them (the entity mirrors).
15. **PLAYER:** looks across the water. **GAME:** a pale figure stands facing away.
    - IF the player stays still → the figure stays still.
    - IF the player takes a step → the figure turns slightly on the *next* step, a half-beat late.
    - IF the player holds the flashlight on it → it vanishes (never attacks in this ward's first half).

### 4. Pump Room (optional)
16. **PLAYER:** enters the Pump Room. **GAME:** grating floor over rushing water, a medical cabinet.
    - IF the player takes the shortcut across the grating → **IF they sprint**, 55% **[WOUND: leg injury]** (the grate gives way). **ELSE (walk, crouch)** → safe.
    - ELSE the player takes the loop through the baths → no risk, longer route.
    - **Reward either way:** the cabinet holds extra supplies and a note.

### 5. The Catwalk (set piece)
17. **PLAYER:** climbs to the catwalk. **GAME:** three sections: solid, rotted, and a gap. The Understudy walks the baths below, mirroring.
    - **IF the player crouches and keeps to solid girders** → silent, clean crossing. The entity loses interest. `SOOTHED +0`.
    - **IF the player sprints and jumps the gap**:
      - IF lands (45%) → fast, loud; entity draws closer. No injury.
      - ELSE (55%) → **[WOUND: leg fracture or sprain]**; limp begins; footsteps +40% louder.
    - **IF the player fails the jump** → falls into the baths below; takes a **sprain**; the Understudy is near but does not attack. The player must stay still or move quietly.
    - **IF the player freezes** → the entity edges closer, then stops. It teaches stillness.

18. **PLAYER:** reaches the switch and throws it. **GAME:** lights surge. The Understudy stops, tilts its head toward the light. First **calm moment**, `SOOTHED +1`.

### 6. Treating a leg wound (if injured)
19. **PLAYER:** kneels at a safe spot (hold Crouch + Interact). **GAME:** inspects the leg.
    - IF the player has the splint kit → splinting interaction at full quality.
      - IF done slowly → mild limp, `CARE +1`.
      - IF rushed (entity nearby, noise) → complication risk rises; limp worsens.
    - ELSE (no kit) → improvised splint; lower quality.
    - **IF untreated for the ward** → at the lift it becomes **[SCAR: Old Break]** (permanent mild limp in cold or wet areas).

### 7. Baths B and the Lift
20. **PLAYER:** crosses the deep pool. **GAME:** swim (silent, but carried items may be dropped if hands are injured) or take the narrow ledge (loud if limping).
21. **PLAYER:** enters the lift. **GAME:** the brass mirror shows Mara and, behind her, a figure carrying every wound she has. Tomas's last line: *"Don't leave them open. It can tell."* **Ward 3.**

---

## WARD 3: THE SURGICAL WING

22. **PLAYER:** steps out. **GAME:** teal tile, caged lights, gurneys. Dry, chemical air.
23. **PLAYER:** explores corridors. **GAME:** finds the nursing log (*Dr. H. sits up with the patients*).
24. **PLAYER:** reaches the Operating Theatre. **GAME:** the first **safe room**. Instruments laid out in Mara's own order. A warm chair beside the table.
    - **IF the player has open wounds** → they can perform **extended treatment** here (long, safe, careful). IF done well → `CARE +`, scars are prevented. ELSE → wounds stay open.
    - **IF the player has completed all treatments** → the room's hum settles; the Understudy does not enter this room.
25. **PLAYER:** goes to the Gallery. **GAME:** looking down, the Understudy stands in the lamp-light. It raises its hand. Mara's hand is already raised. Glass between them.
    - IF the player lowers their hand → it lowers its hand.
    - IF the player keeps it raised → it holds still.
26. **PLAYER:** searches the Instrument Store. **GAME:** jars labelled with patients' names; **VOSS, N.** is empty and warm. Mara: *"These are people."*
27. **PLAYER:** enters Henn's Office (key found in the store). **GAME:** the diagram, two tapes.
    - **IF the player plays both tapes** → learns Henn linked himself, and hears "please be gentle."
      - This primes the player to try calming the entity (the path to Release).
    - ELSE (plays only one) → the second tape can be found later on the Chorus Room's shelf.
28. **GAME:** the service stair door swings open on its own. The Understudy stands at the top. **Ward 4.**

---

## WARD 4: THE MIRROR WARD

29. **PLAYER:** walks the ward. **GAME:** forty beds, tall mirrors. Reflections arrive late.
    - IF the player carries wounds → they show up in the mirrors *first*; later mirrors show **wounds Mara doesn't have**.
30. **PLAYER:** examines the drawings. **GAME:** joined hands; **MARA WILL COME.** Under it, a tally of pencil strokes.
31. **PLAYER:** inspects the Graft Beds. **GAME:** the brass plaque, a floor shaft rising warm like breath.
32. **PLAYER:** reaches Nell's bed. **GAME:** postcard, ribbon, tooth, plaster hand-cast, and the stack of Mara's signature copied by a child's hand.
    - **IF the player lifts the stack** → Mara realises Nell wrote the ledger signature and the postcard.
    - IF the player ignores it → the Playback Room's tape explains it anyway.
33. **PLAYER:** plays the tape in the Playback Room. **GAME:** Nell, age 9, then present-day Nell's voice answers over her.
34. **GAME:** the Understudy stands at the end of the ward. It lifts one open hand.
    - **IF the player approaches and raises their hand** → its palm stops an inch from theirs. Their scars glow on both hands. `SOOTHED +1`. It leads, limping, toward the stair.
    - **ELSE (flees or ignores)** → it steps aside and clears the doorway, but **no** `SOOTHED` credit.
35. **PLAYER:** descends the spiral service stair. **GAME:** floor after floor, warmth increasing, to the boiler house. Radio: **Tomas: *"Come down. It's only fair you hear it from me."*** **Ward 5.**

---

## WARD 5: THE BOILER HOUSE

36. **PLAYER:** enters the Furnace Hall. **GAME:** heat, soot, one firebox glowing without fuel.
37. **PLAYER:** examines the Coal Store. **GAME:** a child's mitten, spectacles, a rosary swept aside.
38. **PLAYER:** meets **Tomas**. **GAME:** he keeps his distance, hands empty.
    - **IF the player listens to the whole confession** (stays in his room) → learns of the eleven thousand tally marks, the chained doors, and why Nell can't be taken.
      - Reveals the stakes: *if the Chorus loses Nell, it screams.*
    - ELSE (leaves early) → the key facts reach the player later via the letters on his cot.
39. **GAME:** the gantry above the flooded pit gives way. Tomas is pinned.
    - **IF the player frees him** (a long, costly interaction) → **[WOUND: serious leg or arm injury]**; Tomas survives, `TOMAS = rescued`. **[SCAR: Tomas's Debt]** if untreated.
    - **ELSE the player leaves him** → Tomas's last line over the radio (*"Tell her I kept the fire."*). `TOMAS = left`.
40. **PLAYER:** treats any wounds (the boiler house has a bench and a kit).
    - **IF an untreated wound is older than a ward** → it develops **infection** (the Ward 1 payoff). IF the player took the disinfectant → infection avoided.
    - ELSE → fever effects begin (blurred vision, hand tremor) until treated.
41. **PLAYER:** goes through the lower door. **GAME:** the stone stair into black water. **Ward 6.**

---

## WARD 6: THE FOUNDATIONS

42. **PLAYER:** descends. **GAME:** pale cords on the walls, pulsing with the player's heartbeat.
43. **PLAYER:** walks the vaults. **GAME:** ripples answer their steps. The Wall of Faces rests in niches.
    - IF the player carries many scars → each one sounds as a soft tone in the chord.
44. **GAME:** the Chorus speaks: *Hello. You hurt. We know. Stay.*
45. **PLAYER:** enters the Chorus Room. **GAME:** the vast dome; Nell on the stone platform; the clock at 2:47 overhead. **The Threshold checkpoint is created here.**
46. **PLAYER:** talks with Nell. **GAME:** her two-layer voice explains the Chorus, and asks what Mara wants.

### The Final Choice (by action)
47. **PLAYER:** acts. **GAME:** reads the choice from what they do.

**IF the player picks up the surgical tools and begins the surgery** → **Severance.**
- The surgery is a hands-on procedure; its success depends on the surgical skill and steadiness built across the game (callus, steady hands, scars).
  - IF successful → cuts the final cord; the room dims. **ENDING 1 OF 3: SEVERANCE.** Mara carries Nell's pain **[SCAR: Nell's Pain]**.
  - IF it fails (tremor, untreated hands) → the cord is **stabilised, not lost**; the player may retry immediately, with no penalty. An elbow-brace aid is always available, so no scar locks the player out.

**IF the player lies down on the platform beside Nell** → **Vessel.**
- **ENDING 2 OF 3: VESSEL.** Mara stays; Nell walks out. **[SCAR: Shared Pulse]**.

**IF the player stays still, speaks calmly, and treats the Chorus's wounds** → **Release** *if the threshold is met.*
- Requires (`CARE ≥ 70%` **and** `SOOTHED ≥ 1` in Wards 2–4) **or** (`CARE ≥ 50%` **and** the **Bedside Care** sequence completed here; Nell teaches it in plain words, so no earlier tape is needed).
  - IF met → **ENDING 3 OF 3: RELEASE.** Mara walks out with Nell. **[SCAR: Clean Hands]**.
  - **ELSE** → the Chorus does not settle; the player is told *"The Chorus does not trust you yet"* and offered the Chapter Select hint (*earliest ward where care dropped*). They can retry, or pick Severance or Vessel.

---

## AFTER THE ENDING

48. **GAME:** ending card names the ending, shows the tracker (◯●◯), and states *how it was reached*. Epilogue postcard.
49. **PLAYER:** picks from the menu:
    - **Continue** → credits.
    - **Play another ending** → Chapter Select. IF Release is locked → shows the reason and the earliest ward to replay. ELSE → plays from the Threshold.
    - **Main menu.**
50. **IF all three endings reached** → unlocks the **Ending Gallery** and **New Game+** (scars carried; the Understudy recognises the player).

---

## FAILURE PATHS (the game never reloads)

- **IF the player's vitals fall too low** (heavy blood loss, severe head trauma) → screen narrows to the hum; **Mara wakes in the last safe room** with her wounds *as they were*, plus **one new scar**. The game continues.
- **IF the player is injured and out of supplies** → the crawl-through route is always available (slower, noisier). Nothing is soft-locked.
- **IF the player ignores the entity's wind-up (from Ward 3)** → they take a zone injury matching what was already hurt. The entity then recoils for 3–5 s, leaving a window to run, close a door, or treat.

---

## QUICK PATH SUMMARIES

| Playstyle | Route | Likely result |
|---|---|---|
| **The Careful Surgeon** | Side door in Ward 1, splint kit, crouch the catwalk, treat every wound, rescue Tomas, soothe in Ward 4 | `CARE` ≥ 90%, Release available; fewest scars |
| **The Risk-Taker** | Reach through glass, sprint the grate, jump the gap, skip treatment | Many scars; Severance or Vessel; Release locked |
| **The Balanced Player** | Mix of both; rescues Tomas; treats most wounds | `CARE` ~70%; Release possible on a knife-edge |
| **The Explorer** | Takes every optional room and document | Longer run; more Henn context, same endings |

## QA CHECKS DERIVED FROM THIS PLAYTHROUGH
- Every branch above has a visible, attributable consequence.
- No branch dead-ends the story; every failure has a recovery.
- `CARE`, `SOOTHED`, `TOMAS` and `SCARS` update at the points listed and show correctly on Chapter Select.
- Each ending's card shows the correct name, tracker state and "how reached" line.
