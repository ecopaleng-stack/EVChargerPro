# EV Charger Pro — Android starter project

This is an initial Android Studio project containing a WebView-based Arabic/English prototype.

## Current prototype
- Defaults: 220 V single-phase and 380 V three-phase.
- Copper and aluminium conductor resistivity with a simple temperature correction.
- Calculates estimated design current and approximate voltage drop for a user-selected cable size.
- Shows cable sizes that satisfy the entered voltage-drop target **only**.
- Language toggle (Arabic/English), selectable reference label (IEC / BS / NEC), and editable default currency (ILS, USD, JOD, EUR).
- Brand-agnostic product catalogue plan: NESCO, ABB, Schneider, Legrand, Hager, Eaton, Siemens and user-added brands.
- Materials checklist with safety reminders.

## Important engineering limitation
This build is **not** a certified cable-sizing or protective-device selection tool. It does not yet verify ampacity tables, installation reference methods, grouping, ambient correction factors, insulation temperature, short-circuit withstand, disconnection times, earthing arrangements, prospective fault current, breaker curves/breaking capacity, RCD/DC detection coordination, SPD requirements, or local authority rules. The voltage-drop calculation uses a simplified conductor-resistance model and omits AC reactance and installation-specific effects. Do not use it as the sole basis for installation or purchasing protective devices.

Before professional release, the app needs:
1. Verified, licensed standards tables and jurisdiction selection.
2. Installation method, cable construction, insulation, number of loaded conductors, ambient temperature, grouping and burial conditions.
3. Protective-device coordination and EVSE manufacturer-specific RCD/DC protection rules.
4. Earthing and fault-loop/disconnection checks.
5. A reviewed product catalogue (breakers, RCD/RCBO, SPD, isolators, sockets/connectors, enclosures, glands, cables and accessories).
6. Independent validation against worked examples and a qualified electrical engineer's review.

## Build APK
Open this folder in Android Studio (Giraffe or newer), allow Gradle sync, then choose:
**Build > Build Bundle(s) / APK(s) > Build APK(s)**.

The build environment used to prepare this starter project did not have the Android SDK or Gradle installed, so an installable APK could not be compiled here. The source project is supplied for Android Studio build and further engineering validation.

## Build APK without installing Android Studio (GitHub Actions)

This project includes `.github/workflows/build-apk.yml` to build the debug APK in GitHub's cloud.

1. Sign in to GitHub in a browser and create a new **public or private repository**.
2. Upload the contents of the `EVChargerPro` folder to the repository (make sure `.github/workflows/build-apk.yml` is included), then commit the files to `main`.
3. Open the repository's **Actions** tab and select **Build EV Charger Pro APK**. If needed, click **Run workflow**.
4. When the run finishes successfully, open the run and download the artifact named **EV-Charger-Pro-debug-APK**.
5. Extract the downloaded artifact. It contains `app-debug.apk`; transfer it to the Android phone and install it. Android may ask you to allow installation from that source.

The APK produced by this workflow is a debug build for testing, not a signed Play Store release. The app is still an early prototype; electrical results must be independently verified by a qualified professional and local regulations before installation.
