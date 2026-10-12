# WebCode Studio

A mobile-friendly web code editor for writing and previewing HTML, CSS, and JavaScript.

## Features

- Separate editors for `index.html`, CSS, and JavaScript
- CodeMirror syntax highlighting and line numbers
- Run code in an Output preview
- Dark and light themes
- Mobile-friendly keyboard toolbar
- Local code persistence using browser storage when available

## Project Status

This repository currently contains the web app in `index.html`. Android packaging is a separate setup step; a successful build and on-device testing are required before calling the APK ready.

## Run the Web App

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Edit HTML, CSS, or JavaScript and select **RUN** to preview your work.

Some browser features, external resources, and local file paths can behave differently inside an embedded preview or Android WebView. Test your project in the target environment.

## Build an Android APK

The Android setup should use Capacitor and an Android project. If those files are not yet present in the repository, add and configure them before running the build.

Typical local build workflow:

1. Install a current Node.js LTS version and Android Studio.
2. Install the project dependencies.
3. Add the Android platform with Capacitor.
4. Sync the web assets to the Android project.
5. Open the Android project in Android Studio or build it with Gradle.
6. Install the debug APK on a test device and verify the app.

If a GitHub Actions workflow is configured for Android builds, open the repository's **Actions** tab and inspect the workflow run. Download its APK artifact only after the run succeeds.

## Code Persistence

The app attempts to save editor content in `localStorage`, with an in-memory fallback. The in-memory fallback does **not** survive closing the app. Persistence should be verified on the target browser/WebView by:

1. Entering sample code in all three editors.
2. Closing and reopening the app.
3. Confirming that HTML, CSS, and JavaScript are still present.
4. Repeating the test after a device restart.

Clearing the app's storage or uninstalling the app can remove locally saved code. Local storage is not a cloud backup.

## Suggested Test Checklist

- [ ] HTML, CSS, and JavaScript editors open correctly
- [ ] **RUN** updates the Output preview
- [ ] Saved code remains after app close/reopen
- [ ] Theme choice behaves as expected
- [ ] Mobile keyboard toolbar does not cover the editor
- [ ] External scripts, stylesheets, and relative paths are tested
- [ ] Android APK installs and launches on a test device

## Contributing

Keep changes focused, test them in a browser and on Android when relevant, and describe any known limitations in the pull request.

## License

No license is specified yet. Add a `LICENSE` file if you want to define how others may use, modify, or distribute this project.
