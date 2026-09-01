# SolChat downloads

The download page for **SolChat**, and the web build it serves.

Live at <https://sahil-solutionone.github.io/solchat-download/>

## What is in here

| | |
|---|---|
| `index.html` | the download page - Android, Web, Windows |
| `app/` | the Flutter web build, exactly as `flutter build web` produced it |

**No source.** This repository is public only because GitHub Pages requires it
to be, and it holds nothing that is not already handed to every device that
installs the app: the compiled bundle and the Supabase *publishable* key, which
is designed to be shipped to clients. The service key, the database and the
private storage buckets are not here and never will be.

Reaching the page gets you a sign-in screen. Every conversation is behind an
account an administrator creates, and the database enforces that on its own.

## Publishing a new build

From the SolChat repository:

```bash
cd app
flutter build web --release --base-href "/solchat-download/app/"
```

Copy `app/build/web` over `app/` here, commit, push. Pages redeploys itself.

The Android APK is **not** stored here. It lives in Supabase and the page links
to the permanent redirect, which always resolves to the newest published build:

```
https://tdhkfrfdqtwyaojuueph.supabase.co/functions/v1/download
```
