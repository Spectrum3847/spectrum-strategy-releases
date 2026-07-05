# Spectrum Strategy — Mobile Releases

This repository hosts the installable mobile builds of Spectrum Strategy so they
can be sideloaded without an app store. The main app repository is private, so
the iOS IPA and the Android APK are published here (public) where installers can
fetch them. You do not normally download files here by hand — you point AltStore
or SideStore (iOS) or Obtainium (Android) at the sources below and they install
and auto-update the app for you.

## iOS — AltStore / SideStore

In AltStore or SideStore, open Sources, add a source, and paste one of these URLs:

- Stable (recommended):

  ```
  https://frcspectrumstrategy-stable.web.app/stable.json
  ```

- Nightly (latest build, may be unstable):

  ```
  https://frcspectrumstrategy-nightly.web.app/nightly.json
  ```

Spectrum Strategy then appears and you can install it; new builds show up as
updates automatically. The installer re-signs the IPA on device with your free
Apple ID, so no paid Apple Developer account is needed. Free signing lasts 7
days, so let AltStore or SideStore refresh the app weekly to keep it working.
The stable source updates with every release; the nightly source updates nightly.

## Android — Obtainium

Android has no AltStore equivalent, so use
[Obtainium](https://github.com/ImranR98/Obtainium), which installs and
auto-updates APKs straight from GitHub releases with no store and no server of
ours.

1. Install Obtainium (from its own GitHub releases or from F-Droid).
2. In Obtainium, add an app using this repository URL:

   ```
   https://github.com/Spectrum3847/spectrum-strategy-mobile-releases
   ```

3. Obtainium finds the latest release APK, installs it, and checks for updates
   from then on.

The first install may prompt you to allow installing from unknown sources. There
is no Google Play listing.

## How it works

- GitHub Actions in the private main repository builds the app: an unsigned iOS
  IPA and an Android APK.
- Each build is uploaded here as a GitHub Release asset. This repo is public, so
  the installers can download the assets without authentication.
- iOS: the AltStore/SideStore source JSON and the app icon are served from
  Firebase Hosting; the installer re-signs the IPA on device.
- Android: Obtainium reads this repo's releases feed and installs the APK
  directly.

## Notes

- These are the team's own builds. Please do not redistribute them outside the team.
- iOS free signing expires after 7 days — refresh weekly in AltStore/SideStore.
