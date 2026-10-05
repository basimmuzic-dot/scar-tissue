# SCAR TISSUE — Game Design Document

*A first-person survival horror game where your body is the save file.*

---

## 1. Executive Summary & Pitch

**Setting:** St. Aldric Sanatorium, sealed after a flood and a fire. You are Dr. Mara Voss, a trauma surgeon who came back for a missing patient. Something in the building imitates the people who died there. It learns from how you move, and from how you are hurt.

**Hook:** Injuries are not a health bar. Every wound is a physical state that changes your controls, senses, sound footprint and options. Wounds are treated, adapted to or carried forward as scars. You are never "reset"; you are only changed.

**Target aesthetics (MDA):** Sensation (bodily dread), Narrative (what happened here), Challenge (managing a failing body), Discovery. Secondary: Submission to a tense, slow pace.

**Psychological hook:** Loss aversion applied to the *self* instead of to items. Players protect their hands because they know what a ruined hand feels like.

---

## 2. Player Experience & Motivation Map

### Player profile (Bartle)
- **Explorers (primary):** the building and its anomalies reward careful looking.
- **Achievers (secondary):** "clean run" and "scar collection" mastery goals.
- Socializers / Killers: not targeted. Optional shared-seed "autopsy reports" for sharing stories.

### SDT
| Need | How it is met |
|---|---|
| **Autonomy** | You choose which risks to take (force the door vs. find the key) and how to treat each wound, including leaving some untreated. |
| **Competence** | Clear cause→effect feedback: you can read why you were hurt. Treatment is a learnable skill, not a lottery. |
| **Relatedness** | Patient case files, voice recordings, and one living NPC (Tomas, a radio voice) you can fail or protect. |

### Octalysis profile
- **White Hat (dominant):** CD1 Meaning (finding the patient, uncovering the truth), CD2 Accomplishment (surgical skill growth), CD3 Creativity (improvised treatments, compensation strategies).
- **Black Hat (constrained):** CD8 Loss & Avoidance (the core tension), CD7 Unpredictability (the entity's behavior), CD6 Scarcity (supplies are enough to survive, not to be perfect; see `TRADEOFFS.md`).
- CD4 Ownership: your scarred body and chosen prosthetics. CD5 is minimal by design.

---

## 3. Core Loop & Mechanics Architecture

### Primary loop (2–5 min)
**Explore → Perceive an anomaly → Choose approach (safe/slow vs. risky/fast) → Resolve → Assess your body → Treat or push on.**

### Secondary loop (per chapter, 30–45 min)
Reach a ward objective → extract a clue and a resource → return to a safe room (the operating theatre) → perform long-form treatment, craft, and review the Body Chart.

### The Body System (the core mechanic)

The body has six zones. Each has independent condition states.

| Zone | Injury types | Mechanical and sensory consequences |
|---|---|---|
| **Hands/Arms** | Laceration, sprain, fracture | Interaction slows; lockpicking/surgery mini-games gain tremor; a broken arm drops what you carry when you sprint. |
| **Legs/Feet** | Fracture, torn tendon, puncture | Limp, reduced speed, **louder footsteps**; can't vault or crouch-sprint. Stairs become a risk. |
| **Torso** | Rib fracture, internal bleed | Breath audible when holding still; stamina caps lower; bleed requires timed pressure. |
| **Head** | Concussion | Camera sway, delayed focus, tinnitus that masks real audio cues. |
| **Eyes** | Burn, debris | Blur, light sensitivity; flashlight becomes a trade-off. |
| **Ears** | Barotrauma | Directional audio degrades, so you lose your best enemy-detection tool. |

### Wound lifecycle
`Fresh → Bleeding/Unstable → Stabilized → Healing → Scar (permanent, mild) | Complication (infection, bad set)`

- **Treatment is physical and diegetic.** You open the Body Chart *in-world* by looking at your own hands/legs. There is no pause menu heal. Splinting, suturing, packing and disinfecting are short hands-on interactions with risk (rushing makes tremor worse; skipping disinfectant raises infection chance later).
- **Treatment takes noise and time.** Some actions are impossible while the entity is near, so triage is a real decision.
- **Permanent consequences.** Untreated or badly treated wounds become **Scars**: small, permanent modifiers (e.g., "Old Break: slight limp in cold wards"). Scars are never run-ending but accumulate into a recognizable character.
- **Compensation mastery.** Players can learn adaptive techniques (shift weight to the good leg, crouch-listen with the good ear). Mastery reduces penalties, so harm becomes a skill problem and not only a punishment.

### Entity ("The Understudy") behavior
- Reacts to **your acoustic and visual state**: limping draws it; stillness with a bleed leaves a trail.
- Mimics sounds of past patients, using your impaired hearing against you.
- Never kills instantly except in scripted, clearly telegraphed sequences. Its attacks injure specific zones, so each encounter has a *readable cost*.

### Fail state
"Death" occurs only when vital systems (blood loss, head trauma) cross a threshold. The player is returned to the last safe room **with the injuries sustained up to that point plus one new scar**. The game continues instead of reloading, so failure becomes narrative, not punishment.

---

## 4. Progression & Active Flow Systems

### Active DDA (player-driven)
Difficulty is steered by choices, never hidden rubber-banding:
- **Risk shortcuts:** jump a gap, force a rusted door, reach into a drain. Faster, but each has a *visible* injury chance (shown through environmental cues, e.g., "the floor is rotten").
- **Triage choices:** treat now (safe, noisy, slow) vs. later (risk of complications).
- **Optional "Hard Surgery" challenges:** high-skill procedures that give permanent *beneficial* adaptations (e.g., a better-set limb).
- **Settings, not secrets:** a Mercy Dial in options adjusts injury severity, labeled honestly.

### Onboarding scaffolding (cognitive load)
1. **Ward 1:** one injury type (laceration) and one treatment (bandage). No entity, only atmosphere.
2. **Ward 2:** introduces legs/noise. First stalking encounter.
3. **Ward 3:** introduces sensory injuries (ears/eyes) and the Body Chart.
4. **Ward 4+:** complications, combined injuries, scar adaptation.

Attention is directed with lighting, sound and the body itself: wounds are shown on the character's hands/legs and via audio, not through UI clutter.

### Pacing
Tension waves of ~6 minutes, followed by guaranteed quiet "recovery" windows in safe rooms, so players always have a path back into Flow instead of drifting into chronic anxiety.

---

## 5. Ethical & Engagement Review

| Check | Status |
|---|---|
| **Dark patterns:** no monetized heals, no timers pushing return visits, no loot-box injuries. | Pass, premium single-player, no live-service layer. |
| **Cognitive overload:** one new body system per ward; Body Chart is diegetic and glanceable. | Pass |
| **Intrinsic vs. extrinsic:** mastery of treatment and adaptation, not points or badges, is the reward. | Pass |
| **Fairness of loss:** every injury is traceable to a visible player decision or telegraphed enemy action. No unavoidable random maiming. | Required in QA |
| **Soft-lock prevention:** supplies always sufficient for a careful path; a minimum "crawl-through" path exists with any injury combination. | Required in QA |
| **Disability representation:** injured/impaired states are portrayed as *adaptation and skill*, never as villainy or monstrousness. Consult disabled players during design. | Required |
| **Gore and trigger handling:** content notes at start; Mercy Dial; option to reduce graphic detail (injuries communicated via sound/animation rather than explicit close-ups); sensory options for tinnitus, blur, and camera sway (reducible to avoid motion sickness). | Required |
| **Retention health:** a single 10–12 hour campaign with a New Game+ using carried scars; no engagement-maximizing loops. | Pass |

---

## 6. Suggested Next Steps
1. Prototype the **leg injury → footstep noise → entity response** chain in greybox. If this loop is tense, the pillar works.
2. Playtest the treatment interactions for feel (fun vs. tedious).
3. Design the Body Chart and scar catalog (target ~30 scars).
4. Run an accessibility and sensitivity review before vertical slice.
