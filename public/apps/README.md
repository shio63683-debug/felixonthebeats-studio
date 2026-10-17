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
This directory contains free, publicly downloadable apps. `--require-screenshots`
enforces five distinct real screenshots per public app; the explicit
`--allow-missing-screenshots` release option leaves screenshot references empty
when no real captures are available.

Creator submissions use the Felix Creator Upload app and are stored separately
on FelixServer under `data/felixserver/creator-program/apps/`. They appear in
the live Store catalog only after an owner approves them; they are not copied
into this public directory.

Paid app packages must never be copied here. On the Felix PC they belong under
`data/felixserver/store-paid/apps/<app-id>/`, with the APK, `app.json`,
`price.json`, icon, and screenshots. That path is excluded by `.gitignore` and
is intended to be served by the authenticated FelixServer only.
