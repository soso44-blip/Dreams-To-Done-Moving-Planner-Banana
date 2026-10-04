# Boxed — PWA bundle for GitHub Pages

A hosted, installable version of **Boxed** (moving planner & box inventory). This
is the live demo: it opens with a sample move already filled in, works offline,
and can be added to a phone's home screen like an app.

## What's in here

| File | What it is |
|------|------------|
| `index.html` | The whole app in one file (demo data seeded) |
| `manifest.webmanifest` | App name, icons, colours — makes it installable |
| `sw.js` | Service worker — caches the app so it works offline |
| `icon-192.png`, `icon-512.png` | App icons |
| `icon-512-maskable.png` | Android adaptive icon |
| `icon-180.png` | iPhone / iPad home-screen icon |
| `favicon-32.png` | Browser tab icon |

Everything uses relative `./` paths, so it works from a project subfolder like
`https://yourname.github.io/boxed/`.

## Put it online (about 3 minutes)

1. Go to GitHub and create a new **public** repository, e.g. `boxed`.
2. On the repo page choose **Add file → Upload files**, drag in *all* the files
   from this folder (not the folder itself — the files), and **Commit**.
3. Open **Settings → Pages**. Under *Build and deployment*, set **Source** to
   *Deploy from a branch*, pick branch **main** and folder **/ (root)**, and
   **Save**.
4. Wait a minute, then reload that Settings → Pages page. It shows your live URL,
   e.g. `https://yourname.github.io/boxed/`. That is your demo link.

Test it on your phone: open the link, then add it to your home screen (Safari:
Share → Add to Home Screen; Chrome: ⋮ → Add to Home screen). It should open full
screen with the Boxed icon, and still work in aeroplane mode.

## Use the link

- Put it in the Etsy listing description as a **free "try it live" demo**.
- Pin it on Pinterest as a free interactive moving tool.

## Want a blank app instead of the seeded demo?

`index.html` ships with sample data so the demo looks full. To host a *blank*
usable version instead, open `index.html`, find this line near the top of the
`<script>`:

```js
const SEED = true;
```

change it to:

```js
const SEED = false;
```

and re-upload. (Anyone already using the demo can also tap **More → Start over**
to clear the sample data.)

## When you change the app later

Edit `index.html`, then **bump the cache version** in `sw.js` — change
`const CACHE = "boxed-v1";` to `"boxed-v2"`, etc. Without this, returning
visitors keep seeing the old cached version. Re-upload both files.
