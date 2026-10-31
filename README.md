# Dino Run

An endless dino runner with power-ups, dragons, coins and skins. It runs in the browser, installs as a PWA, and builds as an Android APK with GitHub Actions.

**Play:** https://acedrdd.github.io/dino-run
**Android APK:** see [Releases](../../releases).

## Gameplay
- Jump over cacti, duck under birds, and outrun raptors (from 2000 points).
- From 4000 points, dragons appear. Each breathes fire once after a short warning. Duck under flying dragons and jump over ground dragons.
- Every 1000 points the score flashes. Day and night alternate as you progress.
- Earn 1 coin for every 5 points, then spend coins on dino skins (Classic, Ocean, Lava, Neon, Gold).

## Power-ups
Pick one up, then use it with the power-up button or `E`.

| Power-up | Effect |
|---|---|
| Armor | Absorbs one hit with a blast that destroys nearby obstacles |
| Slow-Mo | Slows the world for 6 seconds |
| 2x Score | Doubles score gain for 10 seconds |
| Ghost | Pass through obstacles for 5 seconds |
| Double Jump | Jump again in mid-air for 12 seconds |

## Controls
| Action | Keyboard | Touch |
|---|---|---|
| Jump | Space / Up / W | Jump button or tap the screen |
| Crouch | Down / S | Crouch button |
| Power-up | E | Power-up button |
| Pause | P / Esc | Pause button |

## Settings
Open the gear button for sound, volume, vibration, frame-rate cap (Auto/30/60/90/120), graphics quality, FPS counter, orientation, and reset progress. The Skins tab is the coin shop.

Game speed and animation are independent of frame rate. The Android app asks the phone for its highest refresh rate, so it can run at 90 or 120 fps on screens that support it.

## How it's built
The game is a single `index.html` with no dependencies. [Capacitor](https://capacitorjs.com) wraps it as an Android app.

`.github/workflows/build.yml` does two things on every push to `main`:
1. Builds `dino-run.apk` (Actions → latest run → Artifacts). Pushing a tag like `v1.0` also attaches it to a GitHub Release.
2. Deploys the website to GitHub Pages. Set Settings → Pages → Source to "GitHub Actions" once.

You can build everything from a phone: edit files in the GitHub web editor, then run the workflow from the Actions tab.

## Project files
| File | Purpose |
|---|---|
| `index.html` | The whole game |
| `sw.js` | Offline support (bump `CACHE` when you change the game) |
| `manifest.webmanifest`, `icon-*.png` | PWA manifest and icons |
| `package.json`, `capacitor.config.json` | Android wrapper config |

## Saved data
Hi-score, coins, skins and settings are stored locally on the device. Nothing is sent anywhere.
