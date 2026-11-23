# Seamless — Android reconstruction

A fresh Kotlin/Jetpack Compose project using the original application ID (`com.shaikh.seamless`) and the approved Midnight Stream icon artwork.

## What is included
- Local audio library scanning through Android MediaStore (runtime permission required)
- Playback through AndroidX Media3 / ExoPlayer
- Explicit play/pause, previous, next, shuffle and repeat controls
- Seek bar and track list
- Dark interface and initial peach/pink/blue visual identity
- Adaptive launcher icon resources generated from the approved 1254×1254 artwork
- GitHub Actions Android build workflow

## Important reconstruction note
This is a clean reconstruction scaffold, **not a recovery of the original source repository**. The supplied APK contains compiled DEX/resources rather than the original Kotlin source, Gradle project, comments, or build history. The current implementation reproduces core local playback behavior, but does not claim feature parity with every screen or hidden behavior of the APK.

The following requested features are not yet implemented in this baseline: high-quality audio-reactive visualizer engine with 10+ renderers, on-device speech-to-text transcription and synchronized lyric editing, full Liquid Glass theming, metadata-based fallback album-art generation, and the optional home-screen widget. The visual ring currently provides the visual identity but is not an audio-frequency analyser. These are explicitly left out rather than represented by nonfunctional placeholders.

## Build
- Android Studio Ladybug or newer
- JDK 17
- Android SDK Platform 35

Open this folder in Android Studio and sync Gradle. Or run `gradle :app:assembleDebug` with Gradle 8.9+ installed. The GitHub Actions workflow installs Gradle and builds the debug APK on pushes and pull requests.

## Permissions and privacy
The app requests only audio-library read access to list local music. It does not upload audio. Playback uses Media3. No microphone permission is requested in this baseline.

## Known verification status
The project source and workflow are provided, but this environment did not run an Android Gradle build or device/emulator test. Treat the first CI build as the compile verification step; resolve any SDK/plugin download or toolchain issue reported there before release. A release APK must be signed with your own keystore.
