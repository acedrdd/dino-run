# Dino Run

An endless dino runner for the browser and Android. Jump cacti, duck birds, dodge raptors and dragons, grab power-ups, earn coins and unlock skins. Plays in any modern browser, installs as an offline PWA, and builds as an Android APK through GitHub Actions.

**Current version: 2.0**

## How to play

| Action | Touch | Keyboard |
| --- | --- | --- |
| Jump (hold for a higher jump) | JUMP button or tap the game | Space / Up / W |
| Crouch (also fast-falls in the air) | CROUCH button | Down / S |
| Use held power-up | Power-up button | E |
| Pause | Pause button | P / Esc |

The layout follows your device automatically: hold the phone sideways for landscape, upright for portrait.

## Features

### Hearts
You start every run with **3 hearts**. Hitting an obstacle costs one heart, wipes out everything close by and gives you a moment of blinking invulnerability. Lose all three and the run is over.

### Obstacles
- **Cacti** from the start.
- **Birds and raptors** from 2000 points.
- **Dragons** from 4000 points. Each one telegraphs and breathes fire once. Flying dragons: duck. Ground dragons: jump.
- The speed keeps climbing, and the world cycles between day and night.

### Power-ups
Pick up a power-up, then tap the Power-up button to use it (one held at a time).

| Power-up | Effect |
| --- | --- |
| Armor | Absorbs one hit and explodes everything in a blast wave |
| Slow-Mo | Slows the world for 6 seconds |
| 2x Score | Doubles your score gain for 10 seconds |
| Ghost | Pass through obstacles for 5 seconds |
| Double Jump | Jump again in mid-air for 12 seconds |

**Slash (passive, once per run).** One special Slash pickup appears per run, after 800 points. Miss it and it's gone for that run. Grab it and it stays active until you die: whenever you'd get hit, time freezes for 1 second and every obstacle on screen is slashed, then play carries on. It recharges for 8 seconds afterwards, and it's lost when the run ends.

### Coins and skins
- Earn **1 coin for every 25 points**. Coins are saved on your device.
- Open the **Skins** tab (tap the coin counter or use settings) and scroll through **16 skins**. Tap to buy, tap again to equip.

| Skin | Price | Skin | Price |
| --- | --- | --- | --- |
| Classic | Free | Neon | 500 |
| Forest | 50 | Shadow | 650 |
| Ocean | 100 | Frostbite | 800 |
| Crimson | 150 | Gold | 1000 |
| Grape | 200 | Galaxy ★ | 1400 |
| Lava | 250 | Rainbow ★ | 1800 |
| Bubblegum | 300 | Diamond ★ | 2500 |
| Sunset | 350 | Mint | 400 |

Glowing skins leave a sparkle trail. Rainbow breathes through colors and glints.

### Settings
Sound, volume, vibration, frame-rate cap (Auto / 30 / 60 / 90 / 120), graphics quality, FPS counter and reset progress. Frame-rate independent game loop, so physics run the same at any refresh rate.

## Tweaking the game
Constants near the top of the script in `index.html`:

| Constant | Default | What it does |
| --- | --- | --- |
| `COIN_EVERY` | 25 | Score needed per coin (higher = harder) |
| `SLASH_AT` | 800 | Score when the Slash pickup appears |
| `SLASH_COOLDOWN` | 8 | Seconds Slash recharges (0 = none) |
| `UNLOCK` | 2000 | Score when birds and raptors start |
| `DRAGON_AT` | 4000 | Score when dragons start |

## Project files
`index.html` (the whole game), `sw.js` (offline cache), `manifest.webmanifest` and `icon-*.png` (PWA), `capacitor.config.json` and `package.json` (Android build).

When you change any game file, bump `CACHE` in `sw.js` so installed copies update.

## Run and build
- **Web:** open `index.html`, or serve the folder with any static server. Deployed to GitHub Pages by `.github/workflows/build.yml`.
- **Android:** the same workflow builds `dino-run.apk` (Actions > Artifacts, or Releases for `v*` tags).
