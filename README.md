# Mochi-Adventures
# 🐱 The Adventures of Mochi

> A neon space-shooter built on **GenLayer** — featuring Mochi, the galaxy's most fearless cyber-cat.

![GenLayer](https://img.shields.io/badge/Powered%20by-GenLayer-bca2ff?style=flat-square&logoColor=white)
![Firebase](https://img.shields.io/badge/Leaderboard-Firebase-ffd166?style=flat-square)
![HTML5](https://img.shields.io/badge/Built%20with-HTML5%20Canvas-ff5ea8?style=flat-square)

---

## 🎮 About the Game

The Adventures of Mochi is a single-file HTML5 canvas arcade shooter where you pilot **Mochi** — GenLayer's official cyberpunk cat mascot — through relentless alien waves. Clear every wave, defeat the boss, and climb the global leaderboard.

The game runs entirely in the browser. No installs. No dependencies. Just open `index.html`.

---

## 🕹️ How to Play

### Controls

| Action | Keyboard | Mobile |
|--------|----------|--------|
| Move Left | `A` or `←` | ◀ button |
| Move Right | `D` or `→` | ▶ button |
| Fire | `Space` | 🔥 FIRE button |
| Pause | `P` | ⏸ button |

### Objective

- Destroy all aliens in a wave to trigger the **Boss**
- Defeat the Boss to advance to the next level
- Chain kills quickly to build **Combo multipliers**
- Avoid alien shots and body contact
- Enter your callsign after each run to save your score to the **global leaderboard**

---

## 👾 Enemy Types

| Enemy | HP | Description |
|-------|----|-------------|
| **Scout** | 1 | Fast, swooping movement |
| **Spitter** | 1 | Fires 3-way spread shots |
| **Tank** | 3 | Splits into 2 mini-aliens on death |
| **Diver** | 1 | Dives directly at Mochi |
| **Mini** | 1 | Spawned from destroyed Tanks |

---

## ⚡ Powerups

Powerups drop from defeated enemies. Combo chains increase drop chance.

| Powerup | Duration | Effect |
|---------|----------|--------|
| ⚡ **Rapid Fire** | 6s | Doubles your fire rate |
| 🛡️ **Shield** | 8s | Absorbs one hit — glowing purple aura |
| 🌀 **Multi-Shot** | 7s | Fires 3 spread bullets at once |
| 💥 **Screen Blast** | Instant | Destroys all enemies on screen |
| 🐌 **Slow Field** | 5s | Slows all enemies to 35% speed |

---

## 🎯 Difficulty Modes

| Mode | Lives | Score Multiplier | Description |
|------|-------|-----------------|-------------|
| 🟢 **Rookie** | 4 | ×1.0 | Gentler waves, more breathing room |
| 🟡 **Hero** | 3 | ×1.4 | Balanced action, faster waves |
| 🔴 **Legend** | 2 | ×1.9 | Pure neon panic, maximum pressure |

---

## 🏆 Scoring

- Each enemy kill awards base points (60–220 pts depending on type)
- **Combo multiplier** — chain kills within 1.5s for +20 pts per extra kill
- **Wave clear bonus** — 250 pts × difficulty multiplier
- **Boss kill** — 900+ pts × difficulty multiplier (scales with level)
- Higher difficulty = higher score multiplier applied to everything

---

## 🌐 Global Leaderboard

Scores are saved to **Firebase Realtime Database** and shared globally across all players in real time.

- Enter your callsign in the name field after each run
- Hit **💾 Save Score** to push your score to the global board
- Top 20 scores are displayed, sorted by highest score
- The leaderboard is visible on the Home page and the dedicated Leaderboard page

**Firebase Database:** `https://mochi-adventures-default-rtdb.firebaseio.com`

---

## 🚀 Deployment

### Option 1 — Vercel (recommended)

1. Place both files in a folder:
   ```
   mochi-game/
   ├── index.html
   └── vercel.json
   ```
2. Deploy with the Vercel CLI:
   ```bash
   npm i -g vercel
   cd mochi-game
   vercel
   ```
   Or drag the folder onto [vercel.com/new](https://vercel.com/new).

### Option 2 — Any static host

The game is a single `index.html` file. It can be hosted on:
- **GitHub Pages** — push to a repo, enable Pages in settings
- **Netlify** — drag and drop the file
- **Cloudflare Pages** — connect a GitHub repo
- **Any web server** — just serve `index.html` at the root

---

## 🔥 Firebase Setup

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Select your project → **Realtime Database** → **Rules**
3. Set the rules to allow public read and write:
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }
   ```
4. Click **Publish**

> **Note:** For a production game, consider adding authentication or rate-limiting rules to prevent leaderboard abuse.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Game Engine | HTML5 Canvas API (vanilla JS) |
| Rendering | 60fps `requestAnimationFrame` loop |
| Audio | Web Audio API (procedural synth) |
| Leaderboard | Firebase Realtime Database (REST API) |
| Hosting | Vercel (static) |
| Fonts | Space Grotesk (Google Fonts) |
| UI | Pure CSS — no frameworks |

---

## 📁 File Structure

```
mochi-game/
├── index.html      # The entire game — self-contained, ~530KB
│                   # Includes: game engine, UI, Mochi image (base64),
│                   # Firebase integration, all CSS and JS
└── vercel.json     # Vercel routing config for static deployment
```

The Mochi character image is embedded as a base64 data URI inside `index.html` — no external image files needed.

---

## 🎨 Brand & Credits

- **Mochi** is the official mascot of [GenLayer](https://www.genlayer.com)
- Brand colours: `#110fff` (electric blue) · `#bca2ff` (soft purple) · `#282B5D` (deep navy)
- GenLayer brand assets: [genlayer.com/brand-and-press](https://www.genlayer.com/brand-and-press)

---

## 📄 License

This project was built for and is associated with [GenLayer](https://www.genlayer.com).
All Mochi character artwork and GenLayer branding are property of GenLayer Labs Inc.

---

*Made with 💜 and a lot of neon.*