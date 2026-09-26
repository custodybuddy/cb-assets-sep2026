---
name: brand-assets-library
description: Create a reusable CustodyBuddy visual brand asset library from approved reference images before building or refactoring the application UI. Use for logo systems, branded illustrations, decorative assets, empty card/background artwork, asset organization, and an approval showcase.
---

# CustodyBuddy Brand Assets Library

## Purpose

Create the reusable CustodyBuddy visual asset system first.

Do **not** build, redesign, or add application functionality during this phase.

Use the attached approved CustodyBuddy reference images and mood board as the **visual source of truth**.

## This Checkout's Catalog Contract

This repository is a static asset library. Treat `public/brand/asset-manifest.json` as the canonical inventory and `showcase/index.html` as its one review consumer. `public/brand/generated/marketing/import-record.json` preserves original-to-canonical filenames for imported marketing exports.

Before moving, renaming, adding, or removing an asset, inventory its references. For a core asset, update the manifest and the relevant showcase entry together. For generated marketing exports, preserve and update the import record as well. Keep approved reference images and finished marketing exports separate from modular production assets.

Keep `README.md` current when the library's structure or contributor workflow changes. Record material asset, naming, and structural changes in `CHANGELOG.md`; do not use it as a per-file inventory.

Validate the resulting catalog with the repository's built-in JSON/SVG checks and `git diff --check`. Do not add a manifest-to-showcase generator unless a second real consumer demonstrates leverage.

## Workflow

### 1. Analyze the approved references first

Identify and preserve the established CustodyBuddy visual language:

- premium dark legal-tech aesthetic
- deep navy and near-black backgrounds
- restrained blue haze and atmospheric depth
- warm white / cream typography
- gold accents used selectively for emphasis
- thin light-gold borders and dividers
- elegant editorial / modern academic composition
- polished dimensional 3D illustration style
- dark navy leather, paper, glass, metal, and subtle marble-like material cues
- generous negative space for readable UI content
- high contrast and accessible visual hierarchy

The result should feel calm, credible, sophisticated, supportive, and distinctly CustodyBuddy.

Avoid:

- generic law-firm branding
- bright corporate SaaS blue
- generic AI gradients
- excessive glassmorphism
- cartoonish illustrations
- celestial imagery, stars, planets, or glowing orbs
- cluttered legal symbolism
- unnecessary gavels, courthouses, or scales of justice
- decorative effects that reduce readability

If another project is provided as a reference, carry forward only the requested visual quality or illustration approach. Do not copy another brand's identity.

### 2. Audit existing approved assets before creating new ones

Before generating replacements:

- inspect existing CustodyBuddy brand assets
- identify approved assets that should be retained
- identify duplicates, outdated files, or inconsistent variants
- reuse approved assets when practical
- do not redesign the logo or brand identity unnecessarily

Document which assets are reused and which are newly created.

### 3. Create or refine the logo system first

Create or organize:

- primary CustodyBuddy wordmark
- CB monogram
- compact brand mark
- light variant
- dark variant
- favicon / app icon
- horizontal and compact variants where appropriate

Preserve the established direction:

- `Custody` in warm white / cream
- `Buddy` in restrained gold
- elegant serif-led editorial character

Keep logos separate from UI backgrounds.

### 4. Create branded dimensional illustrations

Create reusable branded illustrations for core CustodyBuddy concepts such as:

- Incident Reports
- Legal Document Analysis
- Court Orders
- Communication / Message Review
- Timeline / Event History
- Evidence / Documentation
- Parenting Schedule / Calendar
- Children / Family Context
- Notes / Voice Documentation
- Export / Print / PDF
- Privacy / Security
- AI-assisted Review
- Educational / Legal Information

These are **brand illustrations**, not ordinary interface icons.

Preferred visual language:

- deep navy materials
- warm cream paper
- restrained gold metal accents
- subtle dimensional lighting
- premium legal-document / editorial objects
- calm, polished, trustworthy composition

Keep each illustration separate with a transparent background whenever practical.

Use:

- SVG when the artwork can be represented faithfully as vector artwork
- transparent PNG or WebP for complex 3D, textured, photographic, or dimensional artwork

Do not imitate premium illustrations by simply applying gradients or shadows to Lucide icons.

### 5. Create reusable decorative assets

Create modular visual assets such as:

- thin gold dividers
- restrained gold border treatments
- editorial framing lines
- subtle navy atmospheric gradients
- blue haze / depth treatments
- soft glow elements
- subtle polished-surface textures
- understated legal-document motifs
- decorative shield / document accents where appropriate

Prefer separate assets that can be positioned with CSS.

Do not use decorative assets to communicate essential information.

### 6. Create empty UI artwork

Create reusable visual treatments for:

- hero backgrounds
- section headers
- feature cards
- tool cards
- report / document cards
- educational banners
- article header artwork
- information panels
- empty states
- premium CTA background treatments

Do **not** bake text, buttons, labels, legal information, names, dates, user data, report content, or navigation into images.

React / HTML will render all real content.

Prefer modular pairs such as:

- `incident-report-background`
- `incident-report-illustration`

and:

- `legal-analysis-background`
- `legal-analysis-illustration`

rather than one permanently flattened asset.

### 7. Accessibility rules

Decorative graphics must never carry essential information.

Maintain clean areas for HTML text and data.

Avoid placing:

- bright glow
- detailed illustrations
- gold ornaments
- busy textures
- decorative lines

directly beneath important text or controls.

Artwork must remain understandable and visually balanced at mobile sizes.

Ensure sufficient contrast between artwork and future interface content.

### 8. Performance rules

Prefer:

- SVG for clean vector assets
- WebP where it meaningfully reduces file size without harming quality
- transparent PNG when dimensional detail requires it

Optimize generated raster assets for realistic in-app display sizes.

Avoid unnecessarily huge source files.

Do not export decorative raster assets at dimensions far beyond likely usage unless a high-resolution master is explicitly required.

### 9. Organize the library

Use a structure similar to:

```text
/public/brand/
  /logo/
  /illustrations/
  /backgrounds/
  /decorative/
  /textures/
  /generated/
```

Use semantic filenames.

Examples:

```text
custodybuddy-wordmark-light.svg
custodybuddy-monogram.svg
incident-report-illustration.webp
legal-document-analysis-illustration.webp
communication-review-illustration.webp
feature-card-navy.svg
educational-banner-navy.svg
gold-divider.svg
navy-haze-texture.webp
```

Avoid filenames such as:

```text
image1.png
final-final.png
new-logo2.svg
generated-asset-7.png
```

### 10. Create an asset manifest

Create:

`/public/brand/asset-manifest.json`

For each asset record:

- filename
- purpose
- category
- format
- transparency
- recommended usage
- recommended display size
- whether decorative or meaningful
- alt-text guidance when appropriate
- whether reused or newly created
- source / reference notes when useful

### 11. Build one internal Asset Showcase page

Create one internal Asset Showcase for visual review.

Display:

- logo system
- color palette
- typography direction
- branded illustrations
- decorative assets
- textures
- background / card treatments
- representative assets at desktop and mobile-relevant sizes

The showcase exists only for internal review and approval.

It is **not** part of the production CustodyBuddy application.

## CustodyBuddy Core Palette

Use the approved palette as the default brand foundation:

- Deep Navy: `#020716`
- Rich Navy: `#07152B`
- Haze Blue: `#12345B`
- Warm White: `#F7F3EA`
- Body Text: `#D6DCE8`
- Gold Accent: `#F6BA21`

Gold should remain selective.

Do not allow gold to become the dominant background color.

## Typography Direction

Preserve the established editorial contrast:

- elegant serif display typography for major headings
- clean sans-serif typography for body copy, controls, forms, and supporting text

Use the project's approved type stack when already defined.

Do not introduce new font dependencies merely to imitate a reference image.

## Interface Icon Rule

Use ordinary interface icons for controls and actions.

Branded illustrations and interface icons serve different purposes.

Do not replace simple control icons with large decorative artwork.

If the application uses Lucide React, branded illustrations should complement it rather than imitate it.

## Hard Stop

Do **not** proceed to the application build or UI refactor.

Do not create or modify:

- dashboard functionality
- Incident Report functionality
- Legal Document Analyzer functionality
- Communication Tool functionality
- court-order analysis
- authentication
- database / schema work
- Supabase
- API integrations
- AI workflows
- Make.com automations
- WordPress functionality
- production navigation
- application forms
- business logic

Phase 1 is strictly the reusable **visual brand asset system**.

When complete, report:

1. assets created
2. assets reused
3. file locations
4. formats used
5. assets that could not reasonably be SVG and why
6. visual differences or limitations compared with the approved references
7. important CustodyBuddy concepts that still lack dedicated branded artwork
8. any recommended revisions before Phase 2

Then stop.

Wait for explicit approval before beginning Phase 2.
