# Meridian — releases

The built demo, the download page, and where reports land. **No source lives here** — that is in the private `Aldmere/meridian`.

Three things use this repo, and all three need it to be **public**:

| what | why it must be here |
|---|---|
| **Releases** | `releases/latest/download/...` is a permanent link that always serves the newest build. |
| **`latest.json`** | The game reads it on startup to see whether a newer demo exists. A private repo's raw URL 404s for a player, which would make the check silently useless. |
| **Issues** | Where player reports arrive. Nobody can open an issue on a repo they cannot see. |

## Publishing a build

1. Build: `-executeMethod Meridian.EditorTools.BuildMeridian.Windows`
2. Draft a release tagged `v0.4.2`, attach the exe as **`Meridian-Pre-Alpha-Demo.exe`** — the download link on the page depends on that exact name.
3. Update `latest.json` to the same version, with a line saying what changed.

Step 3 is the one that is easy to forget, and forgetting it tells every existing player they are up to date when they are not.

## The page

`index.html` is served by GitHub Pages from this repo's root — Settings → Pages → deploy from `main` → `/`.
