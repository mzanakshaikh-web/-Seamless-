# Seamless — Android project source

IMPORTANT: This is a source-project archive. **Do not upload this ZIP itself as the Android project.**
Extract it first, then upload/commit the extracted files and folders into the ROOT of your GitHub repository.

After extraction, the repository root should look like this:

    .github/
      workflows/
        android.yml
    app/
      build.gradle.kts
      src/
    build.gradle.kts
    gradle.properties
    settings.gradle.kts
    README.md

Do not put these files inside an extra `Seamless-GitHub-Upload/` folder.

## GitHub upload instructions

1. Extract this ZIP on your phone or computer.
2. Open the extracted folder.
3. In GitHub, open your repository and choose **Add file → Upload files**.
4. Select the extracted project contents (the `app` folder, the Gradle files, README, and `.github` workflow folder), not the ZIP archive.
5. Commit the files to the repository's main/root level.
6. Open **Actions** and run **Seamless Android Build**.

If your phone's file picker hides folders beginning with a dot, create `.github/workflows/android.yml` in GitHub manually and paste the workflow from the extracted file.

## Download the APK

After a successful Actions run, open that run and download the `Seamless-debug-APK` artifact. Extract `app-debug.apk` from the artifact ZIP. The source archive is not an installable APK.

## Build setup

- JDK 17
- Android SDK Platform 35 / Build Tools 35.0.0
- Android Gradle Plugin 8.7.3
- Gradle 8.9
- Kotlin 2.0.21

The GitHub Actions workflow installs Gradle 8.9 directly. This source archive does not include `gradlew` or a Gradle wrapper JAR.

## Implementation and verification limits

This is a reconstruction scaffold, not the original source project. The supplied APK contains compiled DEX/resources, not the original Kotlin source or original build setup. The current baseline includes local MediaStore audio listing, Media3 playback controls, track selection, seek bar, shuffle/repeat toggles, and the approved launcher artwork.

Not implemented in this baseline: a genuine 10+ mode audio-reactive visualizer engine, on-device speech-to-text transcription and synchronized lyric editing, full Liquid Glass theming, metadata-generated fallback album art, background playback service/notification, and the optional home-screen widget. The visual ring is decorative, not an audio-frequency analyser.

The archive has been integrity-tested. A complete Android Gradle compilation has not yet been independently verified.
