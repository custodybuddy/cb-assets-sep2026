# CustodyBuddy Brand Asset Library

This repository is the static, reusable CustodyBuddy visual asset library. It is not an application and has no package manager, build step, or automated test suite.

## Use the Library

`public/brand/asset-manifest.json` is the canonical asset inventory. `showcase/index.html` is the internal browser catalog for visual review.

The manifest groups records by purpose: `coreAssetTypes` (logo, icon, pattern, illustration, and texture), `supportingAssets` (background and decorative), and `internalAssets` (references and generated material). The `icon` and `pattern` groups are intentionally empty until approved reusable assets exist.

- `logo/`, `illustrations/`, `backgrounds/`, `decorative/`, and `textures/` hold reusable production assets.
- `generated/references/` holds approved visual source references. Do not deploy these as library assets.
- `generated/brand-kit/` holds internal orientation boards. They do not replace approved source assets.
- `generated/marketing/` holds finished marketing exports. Its `import-record.json` preserves original-to-canonical filenames.
- `showcase/global.css` holds the internal showcase's shared stylesheet; `showcase/index.html` loads it directly.

Read [docs/brand-kit/README.md](docs/brand-kit/README.md) for source hierarchy and brand direction. The extracted editorial rules live in [docs/brand-kit/design-system.md](docs/brand-kit/design-system.md).

## Asset Changes

Use lowercase, hyphen-separated, descriptive filenames. Keep reusable art modular: artwork must not contain real interface copy, names, dates, or case information.

Before adding, moving, or renaming an asset:

1. Find every existing reference.
2. Update the manifest and relevant showcase entry together.
3. For marketing exports, also update `public/brand/generated/marketing/import-record.json`.
4. Record material naming or structural changes in [CHANGELOG.md](CHANGELOG.md).

## Validate

Run the smallest relevant checks after an edit:

```sh
python3 -m json.tool public/brand/asset-manifest.json >/dev/null
xmllint --noout public/brand/logo/custodybuddy-monogram.svg
git diff --check
```

Open the showcase for visual review when its markup, styles, or referenced visual assets change:

```sh
open showcase/index.html
```

The commands validate syntax and whitespace only. Browser review remains necessary for layout, contrast, image loading, and responsive behavior.
