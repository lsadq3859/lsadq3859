# Native Android Project

Minimum OS: Android 9 / API 28. Compile and target SDK: 36.

The native source, resources, Gradle configuration, signing configuration, and application identity are committed here. Generated Capacitor assets and Gradle wrapper binaries are not committed.

From the repository root, after installing dependencies with Node 22+:

```sh
npm run build
node scripts/prepare-android.mjs
npx cap open android
```

The preparation command restores the official Gradle wrapper scripts and JAR from the locked `@capacitor/cli` Android template, preserves the pinned distribution checksum, bundles licenses, and runs Capacitor sync. It does not need an Android SDK until the native build step.

To build and verify an installable test APK with JDK 21 and Android SDK 36 installed:

```sh
node scripts/build-android.mjs debug
```

See `../ANDROID.md` for Arabic instructions, GitHub Actions downloads, private release signing, versioning, and the device test checklist. Do not run `cap add android` over this project. Do not commit private keystores or `keystore.properties`.