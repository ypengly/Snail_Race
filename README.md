# 🐌⚡ Turbo Snail

<div align="center">

![Three.js](https://img.shields.io/badge/Three.js-r128-black?style=for-the-badge&logo=three.js&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Web Audio](https://img.shields.io/badge/Web_Audio-API-FF6B6B?style=for-the-badge)
![3D](https://img.shields.io/badge/3D-Procedural-22C55E?style=for-the-badge)
![Single File](https://img.shields.io/badge/Single_File-HTML-4CAF50?style=for-the-badge)
![Works Offline](https://img.shields.io/badge/Works-Offline-4CAF50?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

**A colorful, arcade-style 3D racing game built with [Three.js](https://threejs.org/).**

*A normally-slow snail discovers a magical turbo shell and races rabbits, squirrels, and frogs through a giant garden.*

[🎮 How to Run](#-how-to-run-it) • [🕹️ Controls](#-controls) • [🏁 Gameplay](#-gameplay) • [📈 Progression](#-progression) • [🔬 Technical Notes](#-technical-notes)

</div>

---

## 📖 Overview

**Turbo Snail** is a single-file 3D arcade racer where a snail — yes, a snail — gets a magical turbo shell and challenges the fastest animals in the garden to a race.

Everything — **3D models, textures, sound effects, and music** — is generated procedurally in code.

### Core Idea

> **No external assets. No build step. No server.**
>
> The game works fully offline once the page has loaded — it only needs the internet once, to fetch Three.js and the Google Font from a CDN.

---

## 🎮 How to Run It

1. Download **`turbo-snail.html`**
2. **Double-click it** — or open it in any modern browser
   - Chrome · Safari · Firefox · Edge
3. **That's it.** No build step, no server, no install.

### Works Everywhere

- ✅ Desktop
- ✅ Tablet
- ✅ Mobile

### Persistence

Progress is saved automatically to your browser's **local storage** — including:

- Coins
- Upgrades
- Unlocked tracks
- Best times
- Shells
- Missions
- Settings

> ⚠️ **Note:** Progress is tied to that specific browser and device. Clearing site data / local storage will reset it.

---

## 🕹️ Controls

### Desktop

| Key | Action |
|-----|--------|
| `A` / `←` | Move left a lane |
| `D` / `→` | Move right a lane |
| `W` / `↑` | Jump |
| `S` / `↓` (hold) | Slide / duck |
| `Space` (hold) | Turbo boost |
| `Shift` (hold) | Drift (builds turbo meter) |
| `Esc` | Pause |

### Mobile / Touch

| Input | Action |
|-------|--------|
| **Swipe left / right** | Change lane |
| **Swipe up** | Jump |
| **Swipe down** or **⬇ button** | Slide |
| **⬆ button** | Jump |
| **Turbo button** (bottom right) | Hold for boost |

---

## 🏁 Gameplay

Race against **3 AI opponents** across **3 unlockable garden tracks** of increasing difficulty and length:

| # | Track | Theme |
|:-:|-------|-------|
| 1 | 🏡 **Backyard Garden** | Where every race begins |
| 2 | 🥕 **Vegetable Garden** | Bigger obstacles, faster pace |
| 3 | 🌧️ **Rainy Garden** | Wet, slippery, and unforgiving |

**Your rivals:**

- 🐇 **Rabbit** — the one to beat
- 🐿️ **Squirrel** — quick and nimble
- 🐸 **Frog** — jumps unpredictably

### ⚡ The Turbo Meter

Fill your **turbo meter** by:

- Collecting coins and crystals
- Drifting
- Jumping
- **Dodging obstacles at the last second** *(near-misses)*
- Finding shortcuts

Then **hold Turbo** for a big speed boost with:

- A **glowing shell**
- **Camera pull-back**
- **Particle trail**

### 🚧 Obstacles & Hazards

Watch out for:

- 🪨 **Rocks**
- 🪵 **Logs**
- 🐦 **Birds**
- 🟤 **Mud patches**

**Jump** over ground obstacles. **Slide or jump** past birds. Getting hit **costs you speed**.

### 🎁 Hidden Rewards

Look for:

- **Shortcut boost pads**
- **Rare shell fragments** hidden along the track

### 🏆 Winning

Win races to:

- Earn coins
- Unlock the next track
- Progress toward **beating your rival, the Rabbit**

---

## 📈 Progression

### 🛠️ Upgrades

Each upgrade has **multiple levels**, bought with coins:

| Upgrade | Effect |
|---------|--------|
| **Turbo Capacity** | Larger turbo meter |
| **Acceleration** | Faster to top speed |
| **Jump Height** | Clear taller obstacles |
| **Shell Armor** | Take more hits |
| **Coin Magnet** | Attract nearby coins |
| **Handling** | Sharper lane changes |
| **Water Control** | Better grip on wet surfaces |

### 🐚 Shell Collection

**10 collectible shell skins**, bought with:

- Coins
- Rare shell fragments

### 🎯 Missions & Achievements

- **In-game objectives** — win races, use turbo, find shortcuts, etc.
- **Coin / fragment rewards**
- **Long-term achievements**

### 🏆 Tournament Mode

Race **every unlocked track back-to-back** for a combined point total.

### ⚙️ Settings

- Music volume slider
- SFX volume slider
- **Graphics quality:** Low / Medium / High — affects shadow resolution, particle counts, and decoration density

---

## 🔬 Technical Notes

### 📄 Single Self-Contained HTML File

All CSS and JavaScript are inline — trivial to download, share, or host anywhere.

- Just needs a **static file server**
- Or **none at all**

### 🎨 Rendering

- **Three.js r128** — loaded from a CDN
- **ACES filmic tone mapping**
- **Canvas-generated gradient sky** and **ground texture per track**
- **Soft contact shadows**
- **Glossy clearcoat material** on the snail's shell

### 🔊 Audio

Fully procedural via the **Web Audio API**:

- Oscillators
- Noise bursts

**No audio files.**

### 🧩 Internal Organization

The JavaScript is organized internally into **clearly-commented sections** mirroring a typical modular structure:

- Utils
- Save system
- Audio
- Particles
- Characters
- Track generation
- Player physics
- AI
- Camera
- UI
- Meta / progression data
- Game state machine
- Bootstrapping

…even though it ships as **one file for portability**.

### 💾 Save Data

Lives under the **`turboSnailSave_v1`** key in `localStorage`.

---

## ⚠️ Known Scope Simplifications

Honest notes about what's simplified in this build:

### 🏁 Three Tracks, Not Six

**Current:** 3 tracks are included rather than the full six originally envisioned.

**Why it's fine:** Each track reuses a **themed procedural generator** — obstacle/collectible layout, colors, weather — so they still feel distinct.

### 🎮 No "Hard Fail" Game-Over State

**Current:** There's no separate game-over state — finishing last still shows the results screen with a **"Race Again"** option.

**Why it's fine:** It serves the same purpose without punishing the player.

---

## 🌐 Browser Support

| Browser | Status |
|---------|--------|
| Chrome (desktop & mobile) | ✅ Full Support |
| Firefox (desktop & mobile) | ✅ Full Support |
| Safari (desktop & iOS) | ✅ Full Support |
| Edge (desktop) | ✅ Full Support |

> Requires **WebGL** (for Three.js) and **Web Audio API** (for sound). If Web Audio is unavailable, the game continues silently.

---

## 💬 Feedback

> If something looks or feels off, it's most likely a rough edge from **scope-trimming a very large brief down to a single working build** — happy to keep iterating on any part of it:
>
> - More tracks
> - More shells
> - Actual model rigging / animation
> - *(etc.)*

---

## 🗺️ Roadmap

### ✅ Current

- [x] Single-file 3D racing game
- [x] Procedural 3D models and textures
- [x] Procedural WebAudio sound and music
- [x] 3 garden tracks with themed procedural generators
- [x] 3 AI opponents (Rabbit, Squirrel, Frog)
- [x] Turbo meter with near-miss, drift, and jump rewards
- [x] Lane-based movement with jump and slide
- [x] Obstacles (rocks, logs, birds, mud)
- [x] Shortcut boost pads and hidden shell fragments
- [x] 7 upgrades with multiple levels each
- [x] 10 collectible shell skins
- [x] Missions and achievements
- [x] Tournament mode
- [x] Settings with graphics quality options
- [x] LocalStorage save system
- [x] Keyboard and touch controls
- [x] Works offline after first load

### 🔜 Future Ideas

- [ ] Additional garden tracks (up to the full six)
- [ ] More shell skins
- [ ] Real model rigging and animation
- [ ] Additional AI opponents
- [ ] Boss races
- [ ] Ghost replay mode
- [ ] Online leaderboard
- [ ] Daily challenges with fixed seeds
- [ ] Custom livery / paint for the snail

---

## 🤝 Contributing

Contributions are welcome. Please:

1. Fork the repository
2. Keep it **single-file** — no external dependencies or assets
3. Keep it **procedural** — no image files, no audio files
4. Preserve the **internal section organization** — one concern per section
5. Test on both desktop and mobile
6. Submit a Pull Request

### Guidelines

- **Never add a required external dependency** beyond Three.js and the Google Font
- **Never ship copyrighted assets** — everything must be generated in code
- **Preserve accessibility** — keyboard and touch controls must both work
- **Keep it playable offline** after first load

---

## 📜 License

MIT — free to use, modify, and distribute.

---

## 🙏 Acknowledgments

- **Three.js** — for making procedural 3D approachable
- **Web Audio API** — for a game with zero audio files
- **Every slow creature who dreamed of going fast** — this game is for you

---

<div align="center">

### 🐌 RACE. DRIFT. BOOST. WIN. ⚡

**No external assets. No build step. No server.**

**A snail with a turbo shell. What could possibly go wrong?**

<br>

⭐ If you enjoyed this game, consider giving it a star.

<br>

[⬆ Back to Top](#-turbo-snail)

</div>
