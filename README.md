# Public Administration Program (PUBA)

Local Eleventy consumer of `../css-shared`, matching GEO and SSRI conventions.

Run `npm run dev` for http://localhost:8084/ or `npm run build` to generate `_site`.
Shared data and heroes live in `../css-shared/src/data/units/puba/` and
`../css-shared/src/media/heroes/puba/`. Layout helpers are intentionally enabled.

See [the migration notes](https://github.com/cssweb-stack/css-shared/blob/main/docs/puba-migration.md) for source mappings,
validation, and deferred profiles, news-feed content, and shared policy work.

## Work on another computer

Use Node.js 22. Keep both repositories beside each other:

```sh
git clone https://github.com/cssweb-stack/css-shared.git
git clone https://github.com/cssweb-stack/puba.git
cd puba
npm ci
npm run dev
```

If `css-shared` is already cloned, pull its latest `main` instead. PUBA reads
shared templates, styles, JSON, and media directly from that sibling checkout.
Open http://localhost:8084/ to preview. Commit page edits in PUBA; commit shared
changes in css-shared.

## GitHub Pages

Pushes to `main` build and deploy through `.github/workflows/deploy.yml` using
the current `css-shared/main` and `/puba/` path prefix. The workflow also runs
hourly and can be run manually to pick up shared changes without a PUBA commit.
GitHub Pages must use **GitHub Actions** as its source.

To add this checkout in GitHub Desktop, choose **File → Add Local Repository**
and select this `puba` folder. It is already initialized and connected to origin.
