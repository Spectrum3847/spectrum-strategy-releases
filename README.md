# Spectrum Strategy iOS Releases

This repository hosts the unsigned iOS IPA builds for Spectrum Strategy so they
can be installed through AltStore or SideStore. You do not download the IPA from
here directly. Instead you add one of the source URLs below in your installer,
which then downloads and re-signs the app on your device with your own free Apple
ID. No paid Apple Developer account is needed.

## Add a source

In AltStore or SideStore, open Sources, add a source, and paste one of these URLs:

- Stable (recommended):

  ```
  https://frcspectrumstrategy-stable.web.app/stable.json
  ```

- Nightly (latest build, may be unstable):

  ```
  https://frcspectrumstrategy-nightly.web.app/nightly.json
  ```

After adding the source, Spectrum Strategy appears and you can
install it. New builds show up as updates automatically.

The stable source updated with every release. The nightly source
is updated every night.

## How it works

- The app is built unsigned by GitHub Actions in the main repository and the IPA
  is uploaded here as a release asset (public, so the installer can fetch it).
- The AltStore source JSON and app icon are served from Firebase Hosting.
- The installer re-signs the IPA on device with your free Apple ID. Free signing
  lasts 7 days, so let AltStore or SideStore refresh the app weekly to keep it
  working.
  
