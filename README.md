# 2048 — Android App

The 2048 game as a native-feeling Android app (WebView wrapper):

- Splash screen → home → game, mobile-app style flow
- 5 tile themes (Classic, Dark, Neon, Pastel, Ocean)
- Grid sizes 3×3 to 6×6
- AI hint (expectimax) + AI auto-play
- Sound effects (Web Audio) + haptic vibration
- Score / stats persistence, multi-step undo

## Building the APK

The APK is built automatically by GitHub Actions on every push to `main`
(workflow: `.github/workflows/build-apk.yml`). The finished APK is uploaded
as a build artifact named `2048-APK`, and attached to Releases as
`2048.apk`.

To build manually: open in Android Studio, or run `gradle assembleRelease`.

## Structure

- `app/src/main/assets/index.html` — the entire game (single self-contained file)
- `app/src/main/java/.../MainActivity.java` — WebView host activity
- `.github/workflows/build-apk.yml` — CI build
