# 🐌⚡ Turbo Snail

A colorful, arcade-style 3D browser racing game built with [Three.js](https://threejs.org/). A normally-slow snail discovers a magical turbo shell and races rabbits, squirrels, and frogs through a giant garden.

Everything — 3D models, textures, sound effects, and music — is generated procedurally in code. There are no external assets, so the game works fully offline once the page has loaded (it only needs the internet once, to fetch the Three.js library and the Google Font from a CDN).

## How to run it

1. Download `turbo-snail.html`.
2. Double-click it (or open it in any modern browser — Chrome, Safari, Firefox, Edge).
3. That's it — no build step, no server, no install.

It works on desktop, tablet, and mobile. Progress (coins, upgrades, unlocked tracks, best times, shells, missions, settings) is saved automatically to your browser's local storage, so it survives a refresh — but it's tied to that specific browser and device, and clearing site data/local storage will reset it.

## Controls

**Desktop**
| Key | Action |
|---|---|
| `A` / `←` | Move left a lane |
| `D` / `→` | Move right a lane |
| `W` / `↑` | Jump |
| `S` / `↓` (hold) | Slide / duck |
| `Space` (hold) | Turbo boost |
| `Shift` (hold) | Drift (builds turbo meter) |
| `Esc` | Pause |

**Mobile / touch**
- Swipe left/right — change lane
- Swipe up — jump
- Swipe down, or the ⬇ button — slide
- ⬆ button — jump
- Turbo button (bottom right) — hold for boost

## Gameplay

- Race against 3 AI opponents (🐇 Rabbit, 🐿️ Squirrel, 🐸 Frog) across 3 unlockable garden tracks of increasing difficulty and length: **Backyard Garden → Vegetable Garden → Rainy Garden**.
- Fill your **turbo meter** by collecting coins and crystals, drifting, jumping, dodging obstacles at the last second (near-misses), and finding shortcuts — then hold Turbo for a big speed boost with a glowing shell, camera pull-back, and particle trail.
- Watch out for rocks, logs, birds, and mud patches — jump over ground obstacles, slide/jump past birds. Getting hit costs you speed.
- Look for shortcut boost pads and rare shell fragments hidden along the track.
- Win races to earn coins, unlock the next track, and progress toward beating your rival, the Rabbit.

### Progression
- **Upgrades**: Turbo Capacity, Acceleration, Jump Height, Shell Armor, Coin Magnet, Handling, Water Control — each with multiple levels, bought with coins.
- **Shell Collection**: 10 collectible shell skins, bought with coins or rare shell fragments.
- **Missions & Achievements**: in-game objectives (win races, use turbo, find shortcuts, etc.) with coin/fragment rewards, plus a set of long-term achievements.
- **Tournament Mode**: race every unlocked track back-to-back for a combined point total.
- **Settings**: music/SFX volume sliders and a Low/Medium/High graphics quality setting (affects shadow resolution, particle counts, and decoration density).

## Technical notes

- Single self-contained HTML file — all CSS and JavaScript are inline, so it's trivial to download, share, or host anywhere (just needs a static file server, or none at all).
- Rendering: Three.js (r128, loaded from a CDN), with ACES filmic tone mapping, a canvas-generated gradient sky and ground texture per track, soft contact shadows, and a glossy clearcoat material on the snail's shell.
- Audio: fully procedural via the Web Audio API (oscillators/noise bursts) — no audio files.
- The JavaScript is organized internally into clearly-commented sections mirroring a typical modular structure (utils, save system, audio, particles, characters, track generation, player physics, AI, camera, UI, meta/progression data, game state machine, bootstrapping) even though it ships as one file for portability.
- Save data lives under the `turboSnailSave_v1` key in `localStorage`.

### Known scope simplifications
- 3 tracks are included rather than the full six originally envisioned; each track reuses a themed procedural generator (obstacle/collectible layout, colors, weather) so they still feel distinct.
- There's no separate "hard fail" game-over state — finishing last still shows the results screen with a "Race Again" option, which serves the same purpose.

## Feedback

If something looks or feels off, it's most likely a rough edge from scope-trimming a very large brief down to a single working build — happy to keep iterating on any part of it (more tracks, more shells, actual model rigging/animation, etc.).
