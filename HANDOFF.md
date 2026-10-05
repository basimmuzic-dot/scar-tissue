# HANDOFF: Start Here

You are taking over **Scar Tissue**, a 3D first-person survival horror game. This repository contains design documents only. There is no code, no art and no playable build. Your job is to turn the design into a game, starting with a small playable piece and growing from there.

The plan is for you to work with an AI coding assistant using the **`godot-3d-game` skill**. This note says what to do, in what order, and where the traps are.

> **Context.** All of these documents were drafted by an AI in a long design conversation. They are consistent with each other and detailed, but **none of it has been played or tested**. Treat them as a strong first draft, not a settled spec. You own the decisions now.

---

## 1. What the game is (one minute)

Mara Voss, a trauma surgeon, returns to a flooded sanatorium in 1994 to find the sister she once signed away. Injuries are physical states that change how you move and hear (a limp makes footsteps louder, ear damage degrades directional sound). The entity hunting you does not just chase you: it **feels your pain**, mirrors your limp, and can be calmed by good care. How you treat wounds across the game decides which of three endings you earn.

Read `README.md` for the file index and `GDD.md` for the pitch.

---

## 2. Setting up the AI

1. Install the **`godot-3d-game` skill** where your AI tool loads skills. (The project owner has a copy on their computer and will give it to you.)
2. Give the AI this repository so it can read the documents.
3. Tell it up front:
   - **The skill decides technical Godot choices** (engine version, project structure, node patterns, how to run and test). I have not seen the skill, so these documents do not assume anything about it.
   - **These documents decide design intent** (story, tone, mechanics, what the player sees and feels).
   - If the two conflict on a technical point, follow the skill. If they conflict on a design point, follow the documents, and ask the project owner if it matters.
4. Tell it to **work in small, runnable steps** and to run the game after each one. See §5.

---

## 3. Read this first (about 30 minutes)

In order:
1. `README.md`: index
2. `GDD.md`: pitch and core loop
3. `ENTITY_SPEC.md`: the monster's behavior (the most important system)
4. `WARDS_1_2.md`: the vertical slice you will build first
5. `TRADEOFFS.md`: why treatment choices should be hard decisions
6. `PLAYTHROUGH.md`: the whole game as branching steps (useful later as a test script)

Everything else (story, scripts, audio, UI, casting) can wait until the slice works.

---

## 4. What to build, in order

Do **not** ask the AI to build the whole game. Build one proof first.

### Milestone 1: The core loop (greybox, no art)
Goal: prove that **a wound changes how you play, and the entity reacts to it.**
- A first-person character that can walk, crouch, sprint, and see its own hands.
- A **simple blocky level**: one dry corridor, one water area (wading is quiet), and the **catwalk with a gap** from Ward 2 (`WARDS_1_2.md` §2.3).
- **One wound type with consequences:** a leg injury that slows movement, adds a limp, and makes footsteps louder.
- **One entity** with three states only: `DORMANT`, `DRAWN`, `MIRRORING` (`ENTITY_SPEC.md` §3). It senses the player's "pain signature" and copies the player's limp with a short delay. No attacks yet.
- **One treatment interaction:** splinting a leg (hold and guide), with quality that matters.

**Definition of done:** you (or a friend) can play it for five minutes and, without being told, notice *"it limps when I limp."*

If that is not interesting, **stop and fix the loop before building anything else.** Everything else in this repository depends on it.

### Milestone 2: Ward 1 and 2 as a vertical slice
Build out `WARDS_1_2.md`: Admissions (lacerations, bandaging, the silence beat) and the Baths (the catwalk set piece, Tomas's radio, the first sighting). Use `CAMERA_WALKTHROUGH.md` and `WORLD_AND_PLOT.md` for how the spaces should look. Playtest against the criteria in `WARDS_1_2.md` §0.

### Milestone 3: The decision systems
Supplies, scar effects, the trade-offs in `TRADEOFFS.md`, and the care tracker. Tune the numbers by playing.

### Milestone 4 onward: Wards 3 to 6, the endings, audio, UI
Use `WARDS_3_6_SCRIPTS.md`, `MIRROR_WARD_SCENE.md`, `ENDINGS_AND_CHECKPOINTS.md`, `SOUND_DESIGN.md`, `MUSIC.md`, `UI_BRIEFS.md`, `FOUND_DOCUMENTS.md`. Cast and record voices per `VOICE_CASTING.md` when the game is ready for them.

---

## 5. How to work with the AI (rules that save time)

- **One small task at a time**, each ending in something you can run and look at. "Make the character limp when the leg is injured" is good. "Build the sanatorium" is not.
- **Make it run the game** after every change and show you the result (screenshot or a short test), not only "it should work."
- **Commit often**, with one clear change per commit, so you can undo a bad AI step.
- **Ask it to read the relevant document before coding**, and to quote the lines it is implementing. It should not invent mechanics that contradict the documents.
- **Keep placeholders as data, not code.** Injury odds, supply counts, thresholds and timings should be easy to edit in one config file.
- **Do not let it generate large art or audio at this stage.** Greybox shapes and placeholder sounds are enough to judge the design.
- If the AI proposes something that changes the design, **decide yourself** before accepting.

### A starter prompt you can paste
> This repository contains design documents for a horror game called Scar Tissue. Read `README.md`, `GDD.md`, `ENTITY_SPEC.md` and `WARDS_1_2.md`. Using the godot-3d-game skill, create a Godot project and build **Milestone 1** from `HANDOFF.md` section 4: a greybox first-person prototype with a leg-injury system (slower movement, limp, louder footsteps), a simple entity that senses the player's pain and mirrors their limp with a delay, and a splint interaction. Work in small steps. Run the game after each step and show me the result. Put all tunable numbers in one config file. Do not build art, story, or later wards yet.

---

## 6. Things you should know before you start

**Placeholders that need real playtesting**
- Injury chances (such as 55% for the catwalk jump), supply counts ("about 12 of 17 wounds"), and the **Release ending thresholds (70%, or 50% plus Bedside Care)** are invented starting values.

**Known gaps and open decisions**
- **`SCARS.md` still lists 32 scars.** The recommendation (made after the catalog was written, and **not yet applied**) is to ship about **10 distinct scar mechanics** and treat the rest as variants of them, because a typical run only produces 4 to 6 scars and players cannot learn 32 compensation techniques. Decide this before building scar content.
- **Controls are not defined.** `PLAYTHROUGH.md` uses generic action names (Move, Interact, Raise Hands, Listen). Design the actual input scheme yourself.
- **There is no production plan:** no schedule, budget, team size or tooling is specified.
- **The riskiest systems** are the procedural entity mirroring and the ear-injury audio mix. Prototype them early; cut or simplify them if they do not work.
- **Voice, music and sound documents describe what to find and make.** No performers or composer are chosen.

**Sensitive material**
- The game depicts injury, medical procedures, a child character's recorded voice, and themes of guilt and loss. Keep the sensitivity and accessibility notes in `GDD.md`, `SOUND_DESIGN.md` and `UI_BRIEFS.md` (content notes, reduced-graphic mode, motion and flashing options, caption support). Child-performer rules in `VOICE_CASTING.md` apply if you record that role.

**This project is separate from other games.** Do not mix it with any other project or repository.

---

## 7. Checking your own progress

At each milestone, ask:
1. Can someone play this for five minutes and say what the injury system *does*?
2. Does every choice have a visible cost *before* it is made?
3. Is any option clearly dominant (always treat slowly, never treat, always rush)? If so, retune. The tests are in `TRADEOFFS.md` §6.
4. Is there always a way forward, whatever the injuries? Nothing may softlock.

When in doubt, play it, and change the documents to match what you learn. They are there to serve the game, not the other way around.
