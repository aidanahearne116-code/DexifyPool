# DexifyPool APK kit

An Android wrapper around the DexifyPool web game. GitHub builds the APK for you, so you don't need Android Studio.

## Get your APK
1. Create a new GitHub repository.
2. Upload everything in this folder (keep the `.github` folder) and push to the `main` branch.
3. Open the repo's **Actions** tab. The **Build APK** workflow runs on every push, or run it yourself with **Run workflow**.
4. When it finishes, open the run and download the **DexifyPool-apk** artifact. Unzip it to get `app-debug.apk`.
5. Copy the APK to your Android phone and open it. Android will ask you to allow installs from this source.

## Update the game
The game lives in `app/src/main/assets/index.html`. Replace that file with a new version and push. A new APK builds automatically.

## Notes
- The APK is debug-signed, which is fine for installing on your own devices. Publishing to Google Play needs a release build with your own signing key.
- The app opens in landscape. To allow portrait, remove `android:screenOrientation` from `app/src/main/AndroidManifest.xml`.
- The app name, package ID (`com.dexify.pool`) and icon are in `AndroidManifest.xml`, `app/build.gradle` and `res/drawable/ic_launcher.xml`.
- The game's font loads from Google Fonts when online and falls back to the system font offline.
