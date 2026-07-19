# 🚂 Last Train from Hollow Pass

> A story-driven, point-and-click **escape-room mystery** in the style of Haiku Games'
> *Adventure Escape Mysteries* — hand-painted scenes, inventory puzzles, and a slow-burn
> whodunit aboard a snowbound luxury train.

A passenger has vanished from a locked sleeper on the **Nightjar Express**, trapped by an
avalanche at Hollow Pass. You are **Detective Wren**. Work car by car — solving locks,
piecing together clues, and uncovering a fraud that runs deeper than anyone aboard — to
find the truth before the line is cleared.

The entire game is a **single self-contained HTML file**. All artwork, audio, and logic are
embedded — no server, no build step, no dependencies. Just open it in a browser.

---

## ▶️ Play

**Option A — open locally**
1. Download `last-train-from-hollow-pass.html`.
2. Double-click it (or open it in any modern browser).
3. Press **New Game**.

**Option B — host on GitHub Pages**
1. Push this repo to GitHub.
2. Copy `last-train-from-hollow-pass.html` to `index.html` (or set Pages to serve it).
3. Enable **Settings → Pages → Deploy from branch** (`main` / root).
4. Share the published URL — it works on mobile too.

> 💡 Designed mobile-first (portrait, tap-to-interact). On desktop it renders in a phone-shaped frame.

---

## 🎮 How to play

- **Tap the glowing sparkles** to examine objects, collect items, and trigger dialogue.
- **Use an item:** tap it in your bag to select it, then tap where to use it.
- **Combine items:** select one item, then tap another in the bag.
- **💡 Hint** gives a context-aware nudge for your current step.
- **📖 Clue Log** collects every discovery and carries across all six chapters.
- **⚙ Settings:** toggle music and sound effects, show/hide tap labels, or restart.
- Progress **auto-saves per chapter** — the title screen offers **Continue**.

---

## 📖 Chapters & mechanics

Each chapter is one train car — a self-contained escape room — and introduces **one new
puzzle mechanic**, **one story reveal**, and **one new character**.

| # | Chapter | New mechanic |
|---|---------|--------------|
| 1 | The Empty Compartment | Combination lock (numeric) |
| 2 | The Dining Car | Item combining |
| 3 | The Baggage Car | 4-symbol lock + hidden objects |
| 4 | The Conductor's Cabin | Morse-code decode (with audio) |
| 5 | The Observation Car | Timeline reconstruction (3:47 flashback) |
| 6 | The Engine | Deduction & final accusation |

---

## ✨ Features

- **Six fully playable chapters** with a complete mystery, beginning to end.
- **Hand-painted artwork** — six illustrated scenes, a character portrait, cover art, and
  eleven inventory icons, all in a consistent storybook-noir style.
- **Original music + procedural audio** — a looping noir score (chords, bass, and arpeggio)
  plus ambient wind and rail clatter, click / chime / lock SFX, and Morse beeps — all
  generated live with the Web Audio API (no audio files). Music and sound effects toggle
  independently in Settings.
- **Save & continue** via browser storage.
- **Accessibility-minded** — large tap targets, optional tap labels, text-symbol puzzles.
- **Zero dependencies** — one HTML file, ~2.3 MB, runs offline.

---

## 🗂️ Project structure

```
.
├── last-train-from-hollow-pass.html   # the complete, self-contained game
├── Last-Train-from-Hollow-Pass-Design-Doc.md   # game design document
├── README.md
├── LICENSE
└── .gitignore
```

All scenes, icons, and audio are embedded in the HTML as data URIs, so the single file is
the whole game.

---

## 🛠️ Tech

- Vanilla **HTML / CSS / JavaScript** — no frameworks, no build tooling required to play.
- A small data-driven **chapter engine** (`CHAPTERS` table) defines each car's background,
  hotspots, and handlers, so new chapters are quick to author.
- **Web Audio API** for procedural ambience and sound effects.
- **localStorage** for save/continue and settings.

---

## 🗺️ Roadmap

- [x] Chapters 1–6 (complete mystery)
- [x] Illustrated art, procedural audio, save/continue, settings
- [x] Original looping music score (with independent music/SFX toggles)
- [ ] Reveal tap labels only on first inspect (partial: labels flash on press)
- [ ] Per-car ambience variations (distinct soundscape per scene)
- [ ] Mobile shell (e.g. Capacitor) for app-store builds, or a native rebuild (Godot)
- [ ] Additional cases / chapters

See the [design document](Last-Train-from-Hollow-Pass-Design-Doc.md) for the full vision,
cast, and build plan.

---

## 🎨 Credits & assets

- **Original game, story, and design** for this project.
- **Artwork** generated with an AI image model and curated for the game; **audio** is
  generated procedurally at runtime (no third-party audio files).
- Inspired by the *Adventure Escape Mysteries* genre (Haiku Games). This is an original,
  independent work and is **not affiliated with or endorsed by Haiku Games**.

---

## 📄 License

Code released under the **MIT License** (see [LICENSE](LICENSE)). The bundled artwork is
provided for use with this project; if you reuse it elsewhere, please review your image
model's terms. Trademarks and the *Adventure Escape* name belong to their respective owners.
