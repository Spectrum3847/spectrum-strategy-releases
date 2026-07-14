# Spectrum Strategy Releases

This repository hosts the installable builds of Spectrum Strategy so they can
be installed without an app store. The main app repository is private, so the
builds are published here (public) where installers can fetch them: an iOS IPA,
an Android APK, and desktop builds for Windows, macOS, and Linux.

This repo was previously named `spectrum-strategy-mobile-releases`; it was
renamed when desktop builds joined the mobile ones. Old links redirect.

## iOS: AltStore / SideStore

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

## Android: Obtainium

Android has no AltStore equivalent, so use
[Obtainium](https://github.com/ImranR98/Obtainium), which installs and
auto-updates APKs straight from GitHub releases with no store and no server of
ours.

1. Install Obtainium (from its own GitHub releases or from F-Droid).
2. In Obtainium, add an app using this repository URL:

   ```
   https://github.com/Spectrum3847/spectrum-strategy-releases
   ```

3. Obtainium finds the latest release APK, installs it, and checks for updates
   from then on.

The first install may prompt you to allow installing from unknown sources. There
is no Google Play listing.

## Desktop: Windows, macOS, Linux

Every stable release carries three desktop builds as release assets:

- `SpectrumStrategy-windows-x64.zip`: unzip and run the exe. SmartScreen will
  warn because the build is unsigned; pick "More info" then "Run anyway".
- `SpectrumStrategy-macos.zip`: unzip, then right-click the app and pick Open
  the first time (it is unsigned), or clear quarantine with `xattr -cr` on the
  app folder.
- `SpectrumStrategy-linux-x86_64.AppImage`: `chmod +x` the file and run it. The
  app can register itself in the applications menu from Settings.

The app checks this repository for new versions from Settings. On Linux the
AppImage can download and install the update in place and relaunch itself; on
Windows and macOS the app opens the release page for you to grab the new build.

## How it works

- GitHub Actions in the private main repository builds the app: an unsigned iOS
  IPA, an Android APK, and the three desktop bundles.
- Each stable build is uploaded here as a GitHub Release asset. This repo is
  public, so the installers and the in-app update check can download the assets
  without authentication.
- iOS: the AltStore/SideStore source JSON and the app icon are served from
  Firebase Hosting; the installer re-signs the IPA on device.
- Android: Obtainium reads this repo's releases feed and installs the APK
  directly.
- Desktop: the app's update check reads this repo's latest release.

## Notes

- These are the team's own builds. Please do not redistribute them outside the team.
- iOS free signing expires after 7 days; refresh weekly in AltStore/SideStore.
- The desktop builds are unsigned on every platform, hence the one-time OS
  warnings above.
