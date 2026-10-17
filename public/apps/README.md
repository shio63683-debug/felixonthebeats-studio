# FelixStore app files

This directory is the public source for free FelixStore APKs. Each app has its
own folder:

```text
public/apps/<app-id>/
  app.json
  current.apk
  icon.png
  screenshots/
    01.png
    02.png
    03.png
    04.png
    05.png
```

`catalog.json` and `version.json` are generated from the APKs and app metadata
by `android/sync-store-public.js`. APK updates replace `current.apk` and update
the version, SHA-256, size, icon, and screenshot references in the catalog.
Only free/public apps are synchronized here. The publish check requires five
real screenshots for every public app.

Paid app packages must never be copied here. On the Felix PC they belong under
`data/felixserver/store-paid/apps/<app-id>/`, with the APK, `app.json`,
`price.json`, icon, and screenshots. That path is excluded by `.gitignore` and
is intended to be served by the authenticated FelixServer only.
