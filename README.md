# Training Data Library

Mobile-friendly static viewer for a normalized football training-session dataset.

## Contents

- `index.html` — responsive, dependency-free viewer (mobile list/detail, search, categories, diagrams, instructions).
- `unified.json` — compact normalized training dataset (273 sessions, 2,223 exercises).
- `vercel.json` — static Vercel configuration.

## Run locally

From this folder:

```sh
python3 -m http.server 8000
```

Open http://localhost:8000. A local server is needed because browsers block `fetch()` on `file://` pages.

## Deploy

Import this repository into Vercel and select **Other** / no framework. The site is static: no build command, npm install, database, or environment variables are needed. Configure `main` as the production branch.

## Dataset

The normalized `planr-unified-v1` structure pools repeated descriptions, authors, and image URL prefixes. Images are loaded from their original external SVG URLs and are not hosted in this repository. The export records two source HTTP 403 failures; those sessions are not included in the 273 loaded records.

The interactive viewer can download the full dataset or open an alternative JSON export from the user’s device. `unified.json` is the single source of truth; editing it changes the deployed viewer when Vercel rebuilds from `main`.

No license has been specified for the dataset or images.