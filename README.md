# Spectrum Strategy Releases

This repository hosts the installable builds of Spectrum Strategy.

## iOS: AltStore / SideStore

In AltStore, SideStore, or Live Container, open Sources, add a source, and paste one of these URLs:

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
Apple ID, so no paid Apple Developer account is needed. Free signing lasts **7
days**, so let AltStore or SideStore refresh the app weekly to keep it working.
**SideStore lets you refresh on device a computer**! The stable source updates
with every release; the nightly source updates nightly.

## Android: Obtainium

Android has no AltStore equivalent, so use
[Obtainium](https://github.com/ImranR98/Obtainium), which installs and
auto-updates APKs straight from GitHub releases.

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

## Notes

- These are the team's own builds. Please do not redistribute them outside the team.
- iOS free signing expires after 7 days; refresh weekly in AltStore/SideStore.
- The desktop builds are unsigned on every platform, hence the one-time OS
  warnings above.
