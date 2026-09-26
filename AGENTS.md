# Repository Guidelines

## Project Structure

This is a static CustodyBuddy brand-asset library, not an application. Approved reusable assets live in `public/brand/`:

- `logo/`, `illustrations/`, `backgrounds/`, `decorative/`, and `textures/` contain core assets.
- `generated/references/` contains approved visual source references; never treat these as deployable library assets.
- `generated/brand-kit/` contains internal orientation boards; these support review but do not replace approved source assets.
- `generated/marketing/` contains export-ready marketing templates and their source record.
- `asset-manifest.json` is the inventory and usage guidance for core assets.
- `showcase/index.html` is the browser-viewable catalog. Root-level PNG/WebP files are visual references or source material; do not treat them as deployable library assets unless explicitly requested.
- `README.md` explains the library for contributors; `CHANGELOG.md` records material asset, naming, and structural changes.

## Local Review and Validation

There is no `package.json`, build command, formatter, or automated test suite. Open the showcase directly in a browser for visual review:

```sh
open showcase/index.html
```

For edits, validate JSON and SVG markup with built-in tools:

```sh
python3 -m json.tool public/brand/asset-manifest.json >/dev/null
xmllint --noout public/brand/logo/custodybuddy-monogram.svg
git diff --check
```

The Python command checks manifest syntax, `xmllint` checks a changed SVG (repeat for each SVG), and `git diff --check` catches whitespace errors. Browser review is still required for layout, contrast, image loading, and responsive behavior.

## Asset and Markup Conventions

Use lowercase, hyphen-separated descriptive filenames, such as `timeline-event-history-illustration.png`. Keep reusable illustrations, decorative elements, textures, and empty backgrounds separate; do not bake UI copy, names, dates, or case information into core artwork. Preserve the documented palette and store transparent branding/decorative artwork as SVG where practical; use PNG/WebP when raster detail or a marketing export requires it.

When adding or changing a core asset, update both `public/brand/asset-manifest.json` and the relevant `showcase/index.html` entry. Keep HTML accessible: meaningful images need concise `alt` text, while purely decorative images use `alt=""`.

Before moving or renaming an asset, inventory its references. Update the manifest, showcase, and documentation together; also update `generated/marketing/import-record.json` when an imported marketing export changes path. Retain semantic, lowercase, hyphen-separated filenames. Record material structural or naming changes in `CHANGELOG.md`.

## Commits and Pull Requests

Recent commits use brief imperative summaries, for example `Add new SVG background asset for article cards`. Keep commits scoped to one asset set or correction. Pull requests should explain the asset purpose, list changed paths, note manifest/showcase updates, include screenshots for visual changes, and state the validation performed. Do not include private family, legal, or case data in assets, references, or screenshots.
