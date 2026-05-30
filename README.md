# web-projects

A static landing page linking to several browser projects, deployable to GitHub Pages.

## What's here

| Folder | Project | Notes |
| --- | --- | --- |
| `index.html` | Landing page | Links to everything below. |
| `fruit-wobble-game/` | Fruit Wobble Game | Fully standalone single-file HTML game. |
| `poker-lab/` | Poker Lab | Pre-built Vite/React app (static). Optional AI advisor uses a key the user enters at runtime — no secret is stored in this repo. |

## Not in this repo: Research AI

The Research AI is a **Python/Streamlit** app — it needs a running server and cannot
run on GitHub Pages. Deploy it on [Streamlit Community Cloud](https://streamlit.io/cloud)
(keys go in its encrypted *Secrets*, never in source), then edit the Research AI card's
`href` in `index.html` to point at your live `*.streamlit.app` URL.

## Rebuilding Poker Lab

Poker Lab's source lives separately. To refresh the built copy here:

```bash
cd /path/to/poker-lab
npx vite build --base=./
cp -R dist/. /path/to/web-projects/poker-lab/
```

The `--base=./` flag is required so assets resolve inside the Pages subfolder.

## Deploying

Push to GitHub, then enable Pages (Settings → Pages → Deploy from branch → `main` / root).
The `.nojekyll` file disables Jekyll so all files are served as-is.
