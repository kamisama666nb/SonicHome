# Sonic Home — Android TV launcher prototype

Version: 0.1.0-alpha
Target device: Hisense 55E3G Pro / Android 9 (API 28)
Visual direction: Sony-inspired minimal dark UI; not affiliated with Sony or ATV Launcher.

## Implemented in this first source milestone
- Android HOME intent entry point and Leanback launcher entry point
- Installed launcher-app discovery and alphabetical listing
- Large-screen dark UI, app icons, D-pad focus state, click-to-launch
- Long-press app menu: open, app info, uninstall entry point
- Settings shortcuts (system/network/display), app-list refresh, about dialog
- Low-dependency Java UI; no network calls or analytics

## Not yet implemented / needs validation
This is not yet a full ATV Launcher replacement. Widgets, Watch Next / Recommendations, TV input switching, folders, custom ordering, custom tile art, wallpaper selection UX, hide/lock apps, backup/restore, status bar configuration, and optional Home-key redirection are not implemented. OEM Android TV builds may restrict some system settings and HOME-button takeover.

## Build
Open this folder in Android Studio with JDK 17 and Android SDK Platform 35 installed, then build `app` > `assembleDebug`. `minSdk 28` means Android 9 or newer. Gradle wrapper configuration is included; wrapper launcher binaries are not bundled in this source archive.

## Important
The current environment has Java but no Android SDK / Gradle installation, so an APK could not be compiled or device-tested here. Do not treat this alpha source as a verified installable APK. After a build is available, test installation, HOME selection, D-pad navigation, app launch, app info/uninstall, sleep/wake, and memory use on the actual TV.

## Build APK using GitHub Actions (iPhone-friendly)

This repository includes `.github/workflows/android-build.yml`. After uploading the project contents to a GitHub repository:

1. Open the repository in Safari and go to **Actions**.
2. Select **Build Sonic Home APK**.
3. Tap **Run workflow** and confirm.
4. Wait for the run to finish successfully.
5. Open the completed run and download the `sonic-home-debug-apk` artifact. GitHub provides it as a ZIP; extract `app-debug.apk` in the Files app.

A push to `main` or `master` also triggers a build automatically. The workflow builds a debug APK for testing; it is not a Play Store release and has not been tested on a physical Hisense TV until installed there.
