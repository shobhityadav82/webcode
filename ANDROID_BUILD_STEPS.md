# WebCode Studio — Android APK build starter

This folder uses the existing single-file WebCode Studio app and wraps it with Capacitor. It adds a GitHub Actions workflow that builds a **debug APK** and uploads it as an artifact.

## Important
- The existing app already saves editor changes to `localStorage` when the WebView/browser permits it. This version also saves on `pagehide` and when the document becomes hidden. Capacitor's stable `https://localhost` origin is intended to keep that storage between app launches.
- Data is stored locally on the same app installation/device. Clearing app storage or uninstalling the app can erase it. This is not cloud sync.
- The GitHub connector could read the repo but could not write/create a branch (403 permission error). These files have **not** been pushed to GitHub. Upload/merge them into your repo manually.

## Add to your existing GitHub repository
1. Download/extract this ZIP.
2. Copy/replace `index.html`, and add `package.json`, `capacitor.config.json`, `.gitignore`, and `.github/workflows/build-apk.yml` at the repository root.
3. Commit and push these files to the `main` branch. Do not delete any of your existing app content.
4. Open the repository's **Actions** tab and select **Build Android APK**. If it has not run automatically, choose **Run workflow**.
5. Wait for the workflow to finish successfully. Open that run and download the `webcode-studio-debug-apk` artifact ZIP. Extract it to get `app-debug.apk`.
6. Transfer the APK to your Android phone and install it. Android may ask you to allow installation from that file manager/browser. Only install APKs you built or trust.

## Test persistence before relying on it
1. Open the app and enter unique test text in HTML, CSS and JS.
2. Switch tabs and run the preview.
3. Close the app fully and reopen it. Confirm all three editors still show the test text.
4. Repeat after rebooting the phone.
5. Test dark/light theme and the Run preview.

## Current limitations to test
- The Run function rebuilds a preview from the HTML body plus the CSS and JS tabs. Complete-document head tags and relative local assets may not behave exactly like a full website.
- The contact form points at `/api/contact`; no backend is included in this single-file repo, so contact submission may not work in the APK without a configured backend/email fallback.
- This workflow creates a **debug APK**, not a signed release APK for Play Store publishing.
