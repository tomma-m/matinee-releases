# Matinee — Releases

Public release channel for **Matinee**, an Android TV VOD player.

- `version.json` is the update manifest. The app reads it from
  `https://raw.githubusercontent.com/tomma-m/matinee-releases/main/version.json`.
- APKs are attached to [GitHub Releases](../../releases) here, one per tag `vX.Y.Z`.
- Stable channel only, for now.

## Manifest

```json
{
  "versionCode": 100,
  "versionName": "0.1.0",
  "apkUrl": "https://github.com/tomma-m/matinee-releases/releases/download/v0.1.0/matinee-0.1.0.apk",
  "sha256": "<shasum -a 256 of the APK>",
  "releaseNotes": "What changed.",
  "minVersionCode": null
}
```

- `versionCode` is `X*10000 + Y*100 + Z` for tag `vX.Y.Z` (so `v0.1.0` is 100). The app offers an update only when
  it is higher than the installed one.
- `apkUrl` must be `https://`. `sha256` is checked before the APK goes to the installer.
- `minVersionCode` is optional. It's read but nothing is forced yet; the update dialog always has "Later".

Until the first release, `version.json` holds a placeholder at `versionCode` 1, which every real build is already
past, so no update is offered.

## Rollback

Android won't downgrade through the installer. Re-pinning an older manifest only stops devices that haven't updated
yet. To undo a release on devices that already took it, release the old code again as the next patch number.

The template and full notes live in the source repo under `release/`.
