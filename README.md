# Dino Run

Endless dino runner with power-ups (armor, slow-mo, 2x score, ghost, double jump).
Plays in the browser, installs as a PWA, and builds as an Android APK through GitHub Actions.

## What is in the game
- Smooth, refresh-rate-independent game loop (physics and animation run the same at 30/60/90/120 fps). The Android app asks the phone for its highest refresh rate.
- Dragons from 4000 points: each one telegraphs and breathes fire once. Flying dragons: duck. Ground dragons: jump.
- Coins: 1 coin per 5 points, saved on the device. Spend them on dino skins.
- Settings: sound, volume, vibration, frame-rate cap (Auto/30/60/90/120), graphics quality, FPS counter, orientation, reset progress. Pause button too.

Keyboard: Space / Up = jump, Down / S = crouch, E = use power-up, P / Esc = pause.

- Website: deployed by `.github/workflows/build.yml` to GitHub Pages.
- Android: the same workflow builds `dino-run.apk` (Actions > Artifacts, or Releases for `v*` tags).
