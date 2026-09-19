# simple-iptv releases

Built APKs for [simple-iptv](https://github.com/mondo004/simple-iptv), published by CI.

## Two channels

| Release | Holds | Moves when |
| --- | --- | --- |
| [`latest`](https://github.com/mondo004/simple-iptv-releases/releases/tag/latest) | The build friends and family get | A build is promoted by hand |
| [`testing`](https://github.com/mondo004/simple-iptv-releases/releases/tag/testing) | The newest build of `main` | Every merge, automatically |

Devices choose in **Settings → Updates** and default to Stable. `latest` is what GitHub's "Latest"
badge resolves to, so the front page of this repo points at the household build.

## Downloading

**For the Downloader app on a Fire TV or Android TV box** — no redirect, so it works on networks
that filter `githubusercontent.com`:

```
mondo004.github.io/simple-iptv-releases/stable.apk
```

That page, with the build it currently holds and its hash, is at
[mondo004.github.io/simple-iptv-releases/download.html](https://mondo004.github.io/simple-iptv-releases/download.html).
It mirrors `latest` only; grab a test build from its release directly.

**Everything else** should use the release assets, which are what the in-app updater reads:

```
https://github.com/mondo004/simple-iptv-releases/releases/latest/download/simple-iptv-release.apk
```

A plain install leaves the app interpreted and slow to start on weak TV hardware. With adb, install
the matching baseline profile alongside it — `simple-iptv-release.dm` on Android 12+,
`simple-iptv-release-api28.dm` on Android 9–11 (every Fire TV stick), renamed to match the APK's
basename:

```
adb install-multiple -r simple-iptv-release.apk simple-iptv-release.dm
```

`version.json` beside the assets describes the build for the in-app update check.
