# Messages for Android

A small Android app for composing a personal message and viewing it in a chat-style receiver screen. The launcher has an adaptive app icon with a fallback for older Android versions.

## Features

- Write a message with the sender's name.
- View messages in date order, with the date above each group and the time below each message.
- Hold a message to select it. Tap additional messages to select more, then delete the selection or cancel.
- Keep message history on the device between app launches.

The sender and receiver screens are two views in the same app. Messages are stored locally on that device; the app does not send SMS, use a messaging service, or sync history to another phone. Clearing the app's data or uninstalling it removes the saved history.

## Build a release APK

Requirements: Android SDK 37 and a JDK supported by the Gradle wrapper. Open this folder in Android Studio first if you need to install the Android SDK components.

From PowerShell in this project folder, set `JAVA_HOME` to the JDK bundled with Android Studio, then build:

```powershell
$env:JAVA_HOME = "C:\Program Files\Android\Android Studio\jbr"
$env:Path = "$env:JAVA_HOME\bin;$env:Path"
.\gradlew.bat assembleRelease
```

The build output is:

```text
app/build/outputs/apk/release/app-release.apk
```

The checked-in `Messages-icon.apk` is the version 2.6 build with version code 9. To distribute a new build, replace that file with the freshly built APK if you want the repository copy updated, or attach the APK to a GitHub Release.

## Install on Android

Copy the APK to the phone and open it from Files. If Android asks, allow your file manager to install apps from that source, then tap **Install**. The app ID is `com.achatwithbrenda.messages`; the minimum supported Android version is Android 6.0 (API 23).

## Signing and updates

The current release build uses Gradle's local debug signing key for sideloading. Android only accepts an update over an installed copy when the app ID and signing key match. Builds made on another computer or a clean GitHub Actions runner may use a different debug key. For reliable releases across computers, configure a dedicated release key and keep the keystore and passwords out of GitHub source history.
