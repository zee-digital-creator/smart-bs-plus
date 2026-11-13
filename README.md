# Smart BS Plus — reconstructed Android Studio scaffold

This project is a clean, editable Android Studio scaffold based on the uploaded APK's visible package/manifest clues and embedded web app manifest.

## Findings from the APK
- Package name: `com.impresacx.smartbsplus` (confirmed from DEX strings)
- App name: `Smart BS Plus` (embedded web app manifest)
- Web app start origin: `https://css-uat-kpdcl.technoami2.in/` (embedded web app manifest)
- Architecture: Trusted Web Activity (TWA), confirmed by Android Browser Helper/TWA classes and strings in `classes.dex`.

## Important limitations
- APKs contain compiled DEX bytecode, not the original Java/Kotlin source project.
- This is a reconstructed starter project, not a byte-for-byte recovery of the original source.
- The APK's original signing key is not recoverable from this project. A rebuilt APK will have a different signature.
- For the TWA to display without browser UI, the website owner must configure Digital Asset Links at `https://css-uat-kpdcl.technoami2.in/.well-known/assetlinks.json` for the package name and the new signing certificate SHA-256 fingerprint.

## Open in Android Studio
1. Extract this ZIP.
2. Android Studio → Open → select the `smartbsplus_android_project` folder.
3. Allow Gradle sync.
4. Build → Build Bundle(s) / APK(s) → Build APK(s).

If you do not own or administer the website, do not change its backend or access controls. Obtain permission before modifying or redistributing the app.

## Build APK using GitHub Actions (no computer required)
1. Upload this project's contents to your GitHub repository (keep the `.github/workflows/android.yml` file).
2. Open the repository's **Actions** tab.
3. Select **Build Smart BS Plus APK** and tap **Run workflow** (or push a commit to `main`/`master`).
4. When the run finishes successfully, open the run and download the `smartbsplus-debug-apk` artifact.

This workflow creates a debug APK for testing, not a Play Store release build. A TWA may show browser UI unless the website owner configures Digital Asset Links for the APK's signing certificate.
