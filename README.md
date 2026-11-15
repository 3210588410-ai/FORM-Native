# FORM Native iOS starter (Expo / React Native)

This is the first native iOS codebase scaffold for FORM. It is not yet a signed `.ipa` and cannot be installed by tapping this ZIP.

## Current implementation
- Native React Native app shell with FORM dark UI and five tabs
- Macro dashboard; default targets C 160g / P 130g / F 55g
- Energy computed as 4/4/9 = 1,635 kcal
- Add foods by per-100g macros and serving grams
- Meal categories and daily totals
- Seed food library with quick-fill
- Local persistence through AsyncStorage

## Planned next iteration
Training logger, body weight/body-fat log, history editing, JSON/CSV export, image recognition through a secure server-side AI endpoint, and optional iCloud sync are not yet implemented in this native scaffold. The previous PWA ZIP remains a separate prototype.

## Build without owning a Mac
You can use a browser-based development environment such as GitHub Codespaces from your iPhone Safari, then run EAS cloud build. This is more awkward than using a computer but does not require a local Mac. Expo documents cloud iOS builds from any operating system: https://docs.expo.dev/build/

1. Create/sign in to GitHub and create a private repository; upload the contents of this folder.
2. Open the repository in GitHub Codespaces (browser).
3. In the terminal run:
   ```bash
   npm install
   npx expo-doctor
   npm install --global eas-cli
   eas login
   eas build:configure
   ```
4. Create/sign in to an Expo account, then link the project. Replace the placeholder EAS project ID in `app.json` if prompted by `eas build:configure`.
5. For an installable iPhone development build, enroll in the Apple Developer Program and register the iPhone. Then:
   ```bash
   eas device:create
   eas build --platform ios --profile development
   ```
6. Open the build link on the iPhone and install the signed development build. TestFlight distribution requires a paid Apple Developer Program membership and App Store Connect setup.

## Important
- Never paste Apple passwords, 2FA codes, signing certificates, or API keys into chat or source files.
- Do not put AI provider API keys in the app. Use a server-side endpoint.
- Data currently persists locally in the app sandbox. It is not yet synced to iCloud.
- Package versions are a starting template; if Expo reports version mismatch, run `npx expo install --fix`.
