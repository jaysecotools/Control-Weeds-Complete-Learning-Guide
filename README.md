# README — Control Weeds Learning Resource (AHCPMG301)

A two-part interactive learning resource for the unit **AHCPMG301 Control weeds**, written for the **Tasmanian** context and the **Certificate III in Conservation and Ecosystem Management (AHC31424)**.

The resource consists of two standalone HTML files that link to each other and are designed to be used together.

```
index.html                    ← The Ultimate Learning Guide (reference)
tasmanian-prediction.html     ← The Judgement Trainer (prediction-first practice)
```

---

## 1. `index.html` — AHCPMG301 Ultimate Learning Guide

A comprehensive, tab-based reference covering everything in the unit. It is structured as a linear "what to know" guide.

### Tabs

| # | Tab | Content |
|---|-----|---------|
| 1 | Why control? | Economic, environmental, fire, water/soil impacts; weed ecology; Tasmanian context; legislation overview |
| 2 | IPM Principles | Integrated Pest Management as a decision framework, six key components, the IPM decision cycle |
| 3 | Control Methods | Biological, cultural, mechanical, and chemical control; detailed method comparison table; herbicide resistance |
| 4 | Planning | Site assessment, risk assessment, method/timing selection, follow-up planning, field craft (calibration, drift, clean-down, record keeping), pre-departure checklist |
| 5 | Legislation | Biosecurity Act 2019 (Tas), AgVet Chemicals Act, Nature Conservation Act, EPBC Act; General Biosecurity Duty; Codes of Practice; buffer zones |
| 6 | Monitoring | Why/how to monitor, indicators table, monitoring schedule, gorse control case study |
| 7 | Videos | Three embedded YouTube videos with study guidance |
| 8 | Practice | Seven-question knowledge quiz + three real-world scenarios with feedback |
| 9 | Resources | Glossary of key terms and recommended links (NRE Tas, Weeds Australia, APVMA, WeedSmart, etc.) |
| 10 | Case Study | Blackberry along a fenceline — full method comparison and recommendation plan |
| 11 | Bushland Case Study | Boneseed in a coastal reserve — conservation-focused scenario with model answer |
| 12 | Judgement Trainer | Explains how the two resources fit together and gives a suggested study path |
| 13 | 3D Seedbank | Interactive Three.js soil column showing seedbank depletion over 40 years (gorse/blackberry/boneseed profiles) |
| 14 | 3D Stump Cut | Three.js simulator demonstrating the "apply herbicide immediately after cutting" rule with a live efficacy timer |
| 15 | 3D Fenceline | Three.js flyover of the blackberry case study — click any bush for its zone, allowed methods, and buffer rule |

### Features

- **Global search** across all tabs (highlights matches, hides non-matching tabs)
- **Interactive quizzes** with immediate feedback and scoring
- **Three 3D scenes** built with Three.js (loaded via import map from unpkg)
- **Printable** — tab bar, buttons, hero, and 3D scenes are hidden in print; all tab content prints
- Fully responsive down to mobile

### Technical notes

- Three.js r160 is loaded as an ES module from `https://unpkg.com/three@0.160.0/build/three.module.js` via an import map.
- 3D scenes are **lazy-initialised** the first time their tab is opened, and each has a graceful fallback message if Three.js fails to load (e.g., offline).
- All other functionality uses classic (non-module) JavaScript.
- No build step, no server required — just open the file in a modern browser.

---

## 2. `tasmanian-prediction.html` — Tasmanian Judgement Trainer

A **prediction-first** practice companion. Instead of reading answers, you predict the outcome, reveal the answer, and rate your confidence. Learning happens in the gap between expectation and reality.

### Tabs

| Tab | Content |
|-----|---------|
| Foundations | What is a weed, the weed management cycle, why weeds win, mental models |
| Ecology | Cause → Effect → Response prediction cards (disturbance, fire) |
| Failures | Failure cases: spraying in frost, slashing after seed set, spraying before rain |
| Seedbank | Gorse seedbank timeline and persistence predictions |
| Field signals | Waxy leaf beading, red/purple stress, even-aged cohorts, patchy kill |
| Method hierarchy | Five diagnostic questions for method selection + constraint scenarios |
| Planning | Planning structure template, what success/failure looks like over 5–7 years |
| Weed Library | 18 Tasmanian weeds (declared and environmental) with ID notes and NRE Tas links |
| Calendar | Seasonal treatment calendar for key Tasmanian weeds |
| Safety & Legal | Links to Tasmanian codes of practice, Biosecurity Act 2019 obligations, record keeping |
| Quiz | Seven-question quiz with saved progress |
| References | Key Tasmanian reference links |
| Resistance | Herbicide resistance predictions and early warning signals |
| What NOT to do | Failure checklist (Tasmanian edition) |
| Confidence traps | Four traps that catch experienced operators |
| Indigenous | Reflection on Tasmanian Aboriginal land management (acknowledgement, not representation) |
| Micro-scenarios | Eight 1–2 line field decisions with reveal buttons |
| Media | Two embedded videos with pre-watch prediction prompts |

### Features

- **Prediction cards** — reveal answers only after you've committed to a prediction
- **Confidence tracking** — rate Low/Medium/High on each prediction; saved to `localStorage`
- **Micro-scenarios** with reveal toggles
- **Quiz progress saved** automatically to `localStorage`
- **Remembers your last active tab** and whether you've dismissed the "Start here" banner
- **Deep links** — e.g. `tasmanian-prediction.html?tab=ecology`
- **Printable** — interactive elements are hidden in print, all panes print

---

## How the two files work together

| `index.html` (Ultimate Guide) | `tasmanian-prediction.html` (Judgement Trainer) |
|---|---|
| Reference — "what to know" | Practice — "can you predict it?" |
| Linear, tab-by-tab reading | Scaffolded, predict-before-reveal |
| Best for first exposure | Best for reinforcement and self-testing |
| Comprehensive case studies | Micro-scenarios and confidence traps |
| Legislation and planning detail | Ecology and field-signal focus |

Both files contain a prominent link to the other (`companion-link` in `index.html`, `back-link` in `tasmanian-prediction.html`), so learners can move between them freely.

### Suggested study path

1. Read **Why control?** and **IPM Principles** in `index.html`.
2. Open `tasmanian-prediction.html` and work through **Foundations** and **Ecology** — predict before you reveal.
3. Return to `index.html` for **Control Methods**, **Planning**, and **Legislation**.
4. Back to the trainer for **Failures**, **Seedbank**, and **Field signals**.
5. Finish the **Practice** quizzes and both **Case Studies** in `index.html`.
6. End with the trainer's **Confidence traps** and **Micro-scenarios**.

---

## Running the resource

### Requirements

- A modern browser with WebGL support (Chrome, Edge, Firefox, Safari — recent versions)
- An internet connection for:
  - Font Awesome icons (CDN)
  - Google Fonts (Inter — `index.html` only)
  - Three.js (unpkg — `index.html` 3D tabs only)
  - Embedded YouTube videos
  - NRE Tas / Weeds Australia links (clicked by the learner)

### Usage

1. Place both HTML files in the **same folder**.
2. Open `index.html` in a browser.
3. Use the links in each hero section to move between the guide and the trainer.

No server, build step, or installation is required. Both files also work when opened directly from the filesystem (`file://`), though some browsers restrict `localStorage` on `file://` — if quiz/confidence progress doesn't persist, serve the folder with a simple local server (e.g. `python -m http.server`).

### Offline behaviour

- Icons, fonts, videos, and the 3D scenes will not load without an internet connection.
- Each 3D tab displays a clear fallback message rather than failing silently.
- All core text content, quizzes, and prediction cards remain fully functional offline.

---

## Customisation

### Weed library images

The Weed Library in `tasmanian-prediction.html` expects images in a `weeds/` subfolder:

```
weeds/gorse.jpg
weeds/montpelier-broom.jpg
weeds/ragwort.jpg
weeds/pampas-grass.jpg
weeds/boneseed.jpg
weeds/blackberry.jpg
weeds/capeweed.jpg
weeds/banana-passionfruit.jpg
weeds/spear-thistle.jpg
weeds/cotoneaster.jpg
weeds/mirror-bush.jpg
weeds/sweet-pittosporum.jpg
```

If an image is missing, a placeholder is shown automatically via the `onerror` handler, so the page still works without any images.

### Quiz questions

- `index.html`: edit the `.quiz-question` blocks in `#tab7` (each has a `data-correct` attribute).
- `tasmanian-prediction.html`: edit the `quizQuestions` array in the script at the bottom.

### 3D scenes

The Three.js scenes are defined in the classic script in `index.html`:

- `initSeedScene()` — seedbank visualisation (species profiles, seed counts, survival scales are in the `profiles` object)
- `initStumpScene()` — stump cut simulator (the 20-second efficacy window is in `efficacyFromTime()`)
- `initFenceScene()` — fenceline flyover (bush locations, zone rules, and buffer notes are in `bushLocations` and `openBushPanel()`)

---

## Accessibility and inclusion notes

- Both files are keyboard-navigable for tabs, quizzes, and reveal buttons.
- Interactive prediction buttons use `aria-expanded` / `aria-controls`.
- Print styles are provided in both files for learners who prefer paper.
- Colour is never the sole indicator of meaning (labels and icons accompany colour coding).
- The Indigenous tab in the trainer is written as an acknowledgement and reflection prompt, not as a representation of Tasmanian Aboriginal knowledge. It directs learners to engage directly with the Tasmanian Aboriginal Centre and Aboriginal Heritage Tasmania.

---

## Disclaimer

This resource **supports learning** for AHCPMG301. It is **not** a substitute for:

- The current unit assessment requirements
- Product labels and APVMA permits
- Current NRE Tas guidance
- Site-specific risk assessment
- Tasmanian legislation (especially the Biosecurity Act 2019)

Herbicide registrations, control recommendations, and legislation change regularly. Always verify current requirements before starting any weed control program.

---

## Credits

- **Developed by:** Jay Rowley © 2026
- **Unit:** AHCPMG301 Control weeds
- **Qualification:** Certificate III in Conservation and Ecosystem Management (AHC31424)
- **Context:** Tasmania (lutruwita)

Third-party assets: Font Awesome (CDN), Google Fonts — Inter (CDN), Three.js r160 (unpkg), YouTube embeds (respective owners). Weed identification links point to NRE Tas and Weeds Australia.
