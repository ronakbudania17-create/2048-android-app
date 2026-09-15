# 2048 — Android App

The 2048 game as a native-feeling Android app (WebView wrapper):

- Splash screen → home → game, mobile-app style flow
- 5 tile themes (Classic, Dark, Neon, Pastel, Ocean)
- Grid sizes 3×3 to 6×6
- AI hint (expectimax) + AI auto-play
- Sound effects (Web Audio) + haptic vibration
- Score / stats persistence, multi-step undo

## Building the APK

The game source lives as a release asset ([game.html](https://github.com/ronakbudania17-create/2048-android-app/releases/download/v1.0/game.html),
verified by SHA-256 at build time). On every push to `main`, GitHub Actions
(workflow: `.github/workflows/build-apk.yml`) downloads it into
`app/src/main/assets/index.html`, builds a release APK with Gradle, and
uploads it as the `2048-APK` build artifact. The signed APK is also attached
to the [v1.0 release](https://github.com/ronakbudania17-create/2048-android-app/releases/tag/v1.0)
as `2048.apk`.

To build manually: download `game.html` from the release into
`app/src/main/assets/index.html`, then open in Android Studio or run
`gradle assembleRelease`.

## Structure

- `app/src/main/assets/index.html` — the entire game (fetched from the release at build time)
- `app/src/main/java/.../MainActivity.java` — WebView host activity
- `.github/workflows/build-apk.yml` — CI build
