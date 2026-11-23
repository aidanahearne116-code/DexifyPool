# DexifyPool APK kit

An Android wrapper around the DexifyPool web game. GitHub builds the APK for you, so you don't need Android Studio.

## 1. Upload the files
1. Unzip this kit on your device.
2. Open the unzipped folder and upload everything INSIDE it to your repo, not the folder itself. When you're done, the top level of your repo should show `app`, `build.gradle`, `settings.gradle` and `gradle.properties`.
3. Commit the upload.

## 2. Add the build workflow
Folders that start with a dot (like `.github`) are often hidden and skipped by GitHub's upload page, so add it from GitHub itself:
1. In your repo, open the **Actions** tab and click **set up a workflow yourself** (or **New workflow** first).
2. Delete everything in the editor and paste in the contents of `build-apk.yml` from this kit.
3. Click **Commit changes**. That starts the first build.

If `.github/workflows/build-apk.yml` already uploaded fine, skip this step. You can delete the loose `build-apk.yml` from your repo afterwards.

## 3. Get the APK
When the run finishes (about 3 to 5 minutes), open it from the **Actions** tab and download **DexifyPool-apk** at the bottom of the page. Unzip it to get `app-debug.apk`, copy that to your Android phone and open it. Android will ask you to allow installs from that source.

## Update the game
The game lives in `app/src/main/assets/index.html`. Replace that file and push. A new APK builds automatically.

## Notes
- The APK is debug-signed, which is fine for installing on your own devices. Publishing to Google Play needs a release build with your own signing key.
- The app opens in landscape. To allow portrait, remove `android:screenOrientation` from `app/src/main/AndroidManifest.xml`.
- The app name, package ID (`com.dexify.pool`) and icon are in `AndroidManifest.xml`, `app/build.gradle` and the `res/mipmap-*` folders.
- If a build fails, open the red run, click the failed step and copy the error text.
