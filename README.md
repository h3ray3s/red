# Arise 77 (new repo)

This project builds the same app as your old APK (app id `com.arise.system`) with the same signing key, so the new APK installs as an UPDATE over the old one. Do not uninstall the old app. Your progress stays on the phone.

## Put it on GitHub

1. On github.com click New repository, give it a name (for example `arise-77`), keep it empty (no README), and create it.
2. In a terminal, inside this unzipped folder (it must contain `.github`, `www`, `debug.keystore`):

```
git init
git add .
git commit -m "Arise 77 v2"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

3. Open the repo's Actions tab. The workflow "Build Arise 77 APK" runs on every push to main, and you can also start it with Run workflow.
4. When it finishes (about 5 minutes), download `arise-77.apk` from the repo's Releases page (newest build) or from the run's Artifacts.
5. Open the APK on your phone and tap Update. If Android asks, allow installs from your browser or file manager.

## Rules that keep it an update

- Keep `debug.keystore` exactly as it is. Android only updates an app that is signed with the same key.
- Keep the app id in `capacitor.config.json` as `com.arise.system`.
- The workflow gives every build a higher version number (minutes since 1970), so a build from a new repo is always newer than the old one.
- To change the app later, edit `www/index.html`, commit and push.

## Moving to another phone

Install the APK there, then use System, Export backup on the old phone and Import on the new one. Wallpaper, imported books and the alarm sound are not included in backups.

## Convert to app (release build)

Actions tab, "Convert to App (release APK)", Run workflow. It turns `www` into an optimized Android app signed with the same key, so it also installs as an update. Download `arise-77.apk` from Releases.
# red
