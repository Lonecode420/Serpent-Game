# 🐍 SERPENT — The Ultimate Snake Experience

> A feature-packed, visually stunning snake game built with pure HTML, CSS & JavaScript. No dependencies. No build tools. Just drop it on a server and play.

![Game Preview](https://img.shields.io/badge/status-live-00ffcc?style=for-the-badge&labelColor=0a0a0f)
![Mobile Ready](https://img.shields.io/badge/mobile-ready-ff3cac?style=for-the-badge&labelColor=0a0a0f)
![No Dependencies](https://img.shields.io/badge/dependencies-none-7928ca?style=for-the-badge&labelColor=0a0a0f)
![License](https://img.shields.io/badge/license-MIT-ffd700?style=for-the-badge&labelColor=0a0a0f)

---

## 🎮 Play Now

👉 **https://ochys.top/Game.php**

---

## ✨ Features

### 🕹️ Gameplay
- **4 Play Modes** — Amateur, Pro, Elite, and God Mode, each with different speeds, wall rules, and score multipliers
- **Goal System** — Each mode has a score target; hit it to unlock your unique bonus code
- **Bonus Codes** — Cryptographically generated, personalised codes tied to your name, mode, and score
- **Level Progression** — Levels increase as your score climbs, tracked live on screen
- **Bonus Star Food** — Appears every 5 eaten foods for triple points, with a countdown timer
- **Power-ups** — Four types that randomly spawn on the board:
  - 🚀 **Speed Boost** — Double your snake's speed for 5 seconds
  - 🐢 **Slow Time** — Half-speed breathing room for 5 seconds
  - 🛡️ **Shield** — Absorbs one fatal collision
  - 💎 **2× Points** — Double all points earned for 5 seconds

### 🎨 Design
- **Dark & Light themes** — Toggle with one tap, preference saved automatically
- **Animated background grid** with ambient glow orbs
- **Glowing snake** with expressive eyes that follow movement direction
- **Pulsing food** with inner highlight and real-time shadow effects
- **Hexagonal power-up icons** with per-type colour coding
- **Danger pulse effect** — canvas border flashes red when the board gets crowded
- **Score popups** that float up from the eat position
- **Particle burst effects** on level-up, goal reached, and game over
- **Scanline overlay** for a retro-CRT aesthetic
- **Idle animation** — snake swims across the start screen while waiting

### 📱 Mobile Support
- **Floating D-pad** — auto-appears on touch devices, anchored to the game board
- **Swipe gestures** — swipe anywhere on the canvas to steer
- **Auto-scaling canvas** — fills the screen perfectly on any phone or tablet
- **Safe area support** — respects iPhone notch and Android gesture bar
- **Add to Home Screen** — runs like a native app with no browser chrome (iOS & Android)
- **Large tap targets** — all buttons are thumb-friendly (minimum 40×40px)
- **Landscape mode** — adapts layout for horizontal play

### 🔊 Audio
- **Web Audio API** sound effects — eat, bonus, level up, goal achieved, game over
- **Mute toggle** — one tap to silence everything
- **No audio files** — all sounds are generated in real-time

### 🏆 Other
- **Player name entry** — personalises the bonus code and end screen
- **Mini leaderboard** — top 5 scores saved locally across sessions
- **Keyboard shortcuts** — Arrow keys / WASD to move, P to pause, R to restart
- **No install required** — single `.html` file, zero dependencies

---

## 🚀 Getting Started

### Option 1 — Open Directly
Download `index.html` and open it in any modern browser. That's it.

### Option 2 — Serve Locally
```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .
```
Then visit `http://localhost:8080`

### Option 3 — Deploy to VPS
Upload `index.html` to your web server's public directory.

**Nginx example:**
```nginx
server {
    listen 80;
    server_name yourdomain.com;
    root /var/www/serpent-game;
    index index.html;
}
```

**Apache example:**
```apache
<VirtualHost *:80>
    ServerName yourdomain.com
    DocumentRoot /var/www/serpent-game
    DirectoryIndex index.html
</VirtualHost>
```

---

## 🎯 Play Modes

| Mode | Speed | Walls | Goal | Multiplier |
|------|-------|-------|------|------------|
| 🌱 Amateur | Slow | Wrap-around | 5 pts | ×1 |
| 🔥 Pro | Medium | Kill on hit | 15 pts | ×1.5 |
| ⚡ Elite | Fast | Kill on hit | 30 pts | ×2 |
| 💀 God Mode | Maximum | Kill on hit | 50 pts | ×3 |

---

## 🕹️ Controls

| Input | Action |
|-------|--------|
| Arrow Keys / WASD | Move snake |
| P | Pause / Resume |
| R | Restart game |
| Enter | Start game |
| Swipe | Move snake (mobile) |
| D-pad | Move snake (mobile) |

---

## 🏅 Bonus Code System

When a player reaches the goal score for their chosen mode, a unique bonus code is generated:

```
PRO-JOHN-X7K3-18
```

The code format is: `MODE-NAME-HASH-SCORE`

- **MODE** — abbreviated mode name (AMT / PRO / ELT / GOD)
- **NAME** — first 4 characters of the player's name
- **HASH** — 4-character alphanumeric hash derived from name + score
- **SCORE** — the player's final score

Codes can be tapped/clicked to copy to clipboard. Use this system to reward players — validate codes on your backend by checking the format and score threshold.

---

## 📁 Project Structure

```
serpent-game/
│
├── index.html        # The entire game — HTML, CSS & JS in one file
└── README.md         # This file
```

---

## 🛠️ Customisation

All game parameters are in the `MODES` object near the top of the `<script>` tag:

```javascript
const MODES = {
  amateur: { spd: 160, wall: false, goal: 5,  mult: 1   },
  pro:     { spd: 105, wall: true,  goal: 15, mult: 1.5 },
  elite:   { spd: 72,  wall: true,  goal: 30, mult: 2   },
  god:     { spd: 45,  wall: true,  goal: 50, mult: 3   },
};
```

- **`spd`** — milliseconds between each game tick (lower = faster)
- **`wall`** — `true` means hitting a wall kills the snake; `false` means it wraps
- **`goal`** — score required to unlock the bonus code
- **`mult`** — score multiplier applied to every point earned

---

## 🌐 Browser Support

| Browser | Support |
|---------|---------|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari (iOS 14+) | ✅ Full |
| Samsung Internet | ✅ Full |
| Opera | ✅ Full |

Requires: Canvas API, Web Audio API, CSS Custom Properties — all supported in every modern browser since 2019.

---

## 📜 License

MIT License — free to use, modify, and distribute.

---

## 🙌 Credits

Built with ❤️ using:
- [Orbitron](https://fonts.google.com/specimen/Orbitron) — display font
- [Rajdhani](https://fonts.google.com/specimen/Rajdhani) — body font
- [Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono) — monospace font
- Web Audio API for procedural sound effects
- HTML5 Canvas for all rendering

---


