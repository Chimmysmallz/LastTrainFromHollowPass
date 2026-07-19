# Last Train from Hollow Pass
### Game Design Document — v0.1 (Prototype)

A story-driven, point-and-click **escape-room mystery** in the spirit of Haiku Games'
*Adventure Escape Mysteries*: atmospheric chapters, inventory items, hidden-object
scenes, combination/logic puzzles, and a slow-burn whodunit. Designed mobile-first
(portrait, tap-to-interact); prototyped in the browser, portable to a mobile engine later.

---

## 1. Premise

The **Nightjar Express**, a 1920s luxury mountain train, is trapped by an avalanche at
**Hollow Pass**. Overnight, first-class passenger **Eleanor Vance** vanishes from her
locked sleeper compartment. No footprints in the snow. The door was bolted from the inside.

You are **Detective Wren**, the only investigator aboard. Working car by car before the
line is cleared, you must uncover what happened to Eleanor — and why every passenger
seems to be hiding something.

**Hook:** A "locked-room" disappearance on a literally locked-down train. Each train car
is a self-contained escape room with its own secrets, suspects, and a clue that advances
the larger mystery.

---

## 2. Protagonist & Tone

- **Detective Wren** — sharp, dry-witted, observant. Player-surrogate; minimal backstory
  so the player projects onto them. Light first-person narration ("The bolt was thrown
  from the inside. So how did she leave?").
- **Tone:** cozy-noir. Tense and mysterious, never graphic. Golden Age detective fiction
  (Agatha Christie's *Murder on the Orient Express* is the obvious touchstone) with a
  warm, hand-illustrated look.
- **Rating target:** all-ages (suitable for the broad Adventure Escape audience).

---

## 3. Cast (suspects & NPCs)

| Character | Role | Secret (revealed across chapters) |
|---|---|---|
| **Eleanor Vance** | The missing passenger | Was investigating a fraud; kept a coded diary |
| **Mr. Calloway** | Wealthy financier | Eleanor was about to expose him |
| **Marisol** | Cabaret singer, Eleanor's friend | Saw something at 3:47 a.m. |
| **Conductor Pike** | Runs the train | Has a master key to every compartment |
| **Dr. Hale** | Travelling physician | Treated Eleanor the night she vanished |
| **The Porter** | Quiet, ever-present | Knows the train's hidden passages |

---

## 4. Chapter Structure

Each chapter = one train car = one escape room. ~10–15 min each.

1. **The Empty Compartment** *(prototype built)* — Eleanor's sleeper. Establish the
   disappearance; escape the locked room; find her diary. **Cliffhanger:** the diary's
   last entry names a 3:47 a.m. meeting.
2. **The Dining Car** — Confront suspects over a "frozen" dinner scene; a poisoned-glass
   puzzle; recover a torn seating chart.
3. **The Baggage Car** — Hidden-object heavy; a trunk with a 4-symbol lock; discover a
   second secret passenger.
4. **The Conductor's Cabin** — Master-key heist; telegraph/Morse puzzle; learn the train
   was stopped *on purpose*.
5. **The Observation Car** — Confrontation at 3:47 (flashback playable scene); assemble
   the full timeline.
6. **The Engine** *(finale)* — Race against the clearing of the line; final accusation;
   multiple-evidence "solve the case" sequence and reveal.

> Pacing rule (Haiku style): every chapter delivers **one new mechanic**, **one story
> reveal**, and **one new suspect detail**.

---

## 5. Core Mechanics

- **Tap-to-interact:** tap hotspots to inspect, collect, or trigger dialogue.
- **Inventory:** collected items sit in a bottom tray. **Select an item, then tap a
  target** to use it (key→lock, oil→hinge, etc.).
- **Combine items:** some items merge (e.g., *torn photo halves* → *full photo*).
- **Clue Log:** a notebook that auto-records findings (numbers, names, symbols) so players
  never have to memorize codes.
- **Puzzle types:**
  - *Hidden object* — find N items in a scene.
  - *Combination locks* — derive a code from in-scene clues (clock, ticket, calendar).
  - *Logic/arrangement* — order objects, match symbols, route wires/pipes.
  - *Mini-games* — sliding tiles, gear trains, light-the-lamps.
  - *Deduction* — assemble evidence to make an accusation (chapter finales).
- **Hint system:** a star/lightbulb button gives a nudge → then the solution. (Monetizable;
  see §8.)

---

## 6. Mobile UI / Art Direction

- **Orientation:** portrait. One-thumb reachable controls.
- **Layout:**
  - Top: narration / dialogue banner.
  - Center: the scene (illustrated room).
  - Bottom: inventory tray + Clue Log + Hint buttons.
- **Art style:** warm, hand-painted storybook noir — deep blues/teals, brass and lamp-amber
  accents, soft grain. Each car visually distinct (sleeper = velvet & wood; dining =
  white linen & candlelight; engine = steel & firelight).
- **Audio:** ambient train clatter + wind; a wistful jazz-noir theme; soft "click/chime"
  feedback on solves.
- **Accessibility:** large tap targets, colour-blind-safe puzzle cues (shape + colour),
  optional text size, skippable mini-games after repeated failure.

---

## 7. Narrative & Progression

- **Linear chapters**, gated by solving the current car. Light backtracking within a car.
- **Evidence board** (meta): unlocked clues accumulate across chapters; the finale checks
  what the player has gathered.
- **Save:** auto-save per chapter; resume mid-chapter.

---

## 8. Monetization (Adventure Escape model)

- **Free to play**, full story playable without paying.
- **Hint currency** ("Lantern Oil"): earn slowly, buy more, or watch a rewarded ad.
- **Optional cosmetics:** detective outfits, train skins.
- **No paywalls on story progression** — this is core to the genre's goodwill.

---

## 9. Build Roadmap

| Phase | Deliverable |
|---|---|
| **0 — Prototype** *(now)* | Playable Chapter 1 in browser (this package). Validate the tap/inventory/lock loop. |
| **1 — Vertical slice** | Chapter 1 polished with art + audio; reusable engine (scene loader, inventory, lock, clue log). |
| **2 — Content** | Chapters 2–4 authored in a data-driven format (JSON scenes). |
| **3 — Finale + meta** | Chapters 5–6, evidence board, deduction finale. |
| **4 — Port & ship** | Wrap in a mobile shell (Capacitor/Cordova for the HTML build, or rebuild in Godot/Unity for native polish). |

**Tech recommendation:** keep the prototype as data-driven HTML/JS. If you later want
native performance, animation, and store features, **Godot** is the cleanest port for a
2D point-and-click; **Unity** if you want the largest asset ecosystem.

---

## 10. Chapter 1 Spec (as built in the prototype)

**Goal:** Escape Eleanor's locked sleeper and recover her diary.

**Solve path:**
1. Search the **pillow** → *Brass Key*.
2. Search the **coat** → *Ticket Stub* ("Berth 9 · Car 3").
3. Inspect the **clock** → frozen at **3:47** (drawer code clue).
4. Open the **drawer** with code **347** → *Padlock Key* + a scratched **photograph**.
5. Open the **jewelry box** with the *Brass Key* → *Door Key* + an engraved ring.
6. Unlock **Eleanor's diary** with the *Padlock Key* → read her final entry (the reveal).
7. Use the *Door Key* on the **door** (only after reading the diary) → **chapter complete**
   → cliffhanger leading to Chapter 2.

Mechanics introduced: tap-to-search, inventory use, a combination lock, key/lock matching,
and the Clue Log.

---

*Next step after you review: I'll refine anything here you want changed, then we expand the
engine to data-driven scenes so Chapters 2–6 are fast to author.*
