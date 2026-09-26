# CustodyBuddy Design System

Status: reference system extracted from `showcase/templates/blog-homepage.html` on 2026-09-26. This describes an editorial blog and resource surface; it does not authorize product UI, new application behavior, or a logo redesign.

## 1. Design Intent

CustodyBuddy presents difficult family-documentation work with calm authority. The system pairs a near-black navy field with cream editorial typography, restrained gold emphasis, thin rules, generous content space, and dimensional brand art that never carries essential information.

Use this system for public educational and marketing surfaces. Keep legal guidance, user data, labels, controls, dates, and status text in accessible HTML.

### Principles

1. **Calm before clever.** Use depth and contrast to organize content, not visual noise.
2. **Editorial hierarchy.** Serif display type introduces sections; system sans-serif carries reading and interaction.
3. **Gold is a signal.** Reserve it for active state, focus, primary action, and small emphasis.
4. **Artwork supports content.** Reusable art is modular, quiet around copy, and never substitutes for a label.
5. **One dark mode.** The extracted template is a fixed deep-navy theme. Do not add a light mode or status palette without a separate approved decision.

## 2. Token Foundation

The template is plain HTML/CSS. Keep its existing custom properties as the source of truth; application-specific component tokens belong in a future application, not this asset library.

```css
:root {
  /* Brand and surface */
  --color-deep-navy: #020716;
  --color-rich-navy: #07152b;
  --color-haze-blue: #12345b;
  --color-surface-raised: #031023;
  --color-surface-newsletter-start: #071b35;
  --color-surface-newsletter-end: #030a18;

  /* Text and emphasis */
  --color-text-primary: #f7f3ea;
  --color-text-secondary: #d6dce8;
  --color-text-muted: #9aa9bc;
  --color-accent: #f6ba21;
  --color-accent-soft: #ffd46d;
  --color-rule: rgb(255 212 109 / 42%);
  --color-rule-strong: rgb(255 212 109 / 72%);

  /* Layout and interaction */
  --content-width: 75rem;
  --control-size: 2.75rem;
  --focus-width: 3px;
  --focus-offset: 4px;
}
```

### Semantic use

| Token | Use | Do not use for |
| --- | --- | --- |
| `--color-deep-navy` | Page background, inverse text on gold | A pure black substitute |
| `--color-rich-navy` | Cards and navigation popovers | Main page field |
| `--color-haze-blue` | Atmospheric art and supportive depth | High-priority action |
| `--color-text-primary` | Headings and highest-priority copy | Muted metadata |
| `--color-text-secondary` | Body text and navigation | Disabled state |
| `--color-text-muted` | Dates, counts, helper text | Essential warnings or controls |
| `--color-accent` | Focus, active state, primary actions | Large background fields |
| `--color-accent-soft` | Hover state, kicker, serif emphasis | Primary button fill |
| Rule tokens | Hairline division and card structure | Heavy separators |

### Contrast reference

These ratios are calculated against flat extracted colors; verify text over an image or gradient independently.

| Foreground | Background | Ratio | Intended text use |
| --- | --- | ---: | --- |
| Warm White | Deep Navy | 18.15:1 | Primary headings and body |
| Body Text | Deep Navy | 14.61:1 | Body copy |
| Muted Text | Deep Navy | 8.40:1 | Metadata |
| Gold | Deep Navy | 11.45:1 | Focus and active states |
| Gold Soft | Rich Navy | 12.93:1 | Hover and kicker copy |
| Deep Navy | Gold | 11.45:1 | Primary button label |

## 3. Typography

| Role | Family | Size | Line height | Weight | Use |
| --- | --- | --- | --- | --- | --- |
| Display 1 | Georgia, `Times New Roman`, serif | `clamp(3.25rem, 7vw, 6.35rem)` | 1.04 | 400 | Blog hero only |
| Display 1 mobile | Same | `clamp(3rem, 16vw, 4.5rem)` | 1.04 | 400 | Narrow hero |
| Display 2 | Same | `clamp(1.45rem, 2.5vw, 2rem)` | 1.04 | 400 | Article-card title |
| Display 3 | Same | 1.60rem | 1.04 | 400 | Newsletter heading |
| Display 4 | Same | 1.45rem / 1.35rem | 1.04 | 400 | Sidebar and resource headings |
| Body | Inter, system sans-serif | 1rem | 1.55 | 400 | Reading copy |
| Lead | Same | `clamp(1.05rem, 2vw, 1.25rem)` | 1.55 | 400 | Hero copy |
| Kicker | Same | 0.90rem | normal | 700 | Uppercase category lead |
| Category | Same | 0.78rem | normal | 700 | Article category |
| Metadata | Same | 0.76–0.92rem | 1.3–1.55 | 400–600 | Dates, counts, sort label |

Use the serif face only for hierarchy. Keep body, navigation, buttons, inputs, and metadata in the system sans-serif stack. Hero display text may use `letter-spacing: -0.045em`; compact labels use positive tracking only when uppercase.

## 4. Spacing, Sizing, and Shape

The template uses a 4px-based rhythm with a few content-driven exceptions. Prefer these steps for new work:

| Token | Value | Template evidence | Use |
| --- | --- | --- | --- |
| `--space-1` | 0.25rem / 4px | Focus offset | Tiny optical correction |
| `--space-2` | 0.50rem / 8px | Topic and small list gaps | Compact grouping |
| `--space-3` | 0.75rem / 12px | Inputs, menu links | Control interior spacing |
| `--space-4` | 1rem / 16px | Card and grid gaps | Default local gap |
| `--space-5` | 1.25rem / 20px | Footer links, heading margin | Medium grouping |
| `--space-6` | 1.50rem / 24px | Sidebar columns | Related-section gap |
| `--space-8` | 2rem / 32px | Header and layout gap | Major local separation |
| `--space-10` | 2.50rem / 40px | Content gutter | Page section interior |
| `--space-18` | 4.50rem / 72px | Hero and content end | Major section breathing room |

| Property | Extracted values | Rule |
| --- | --- | --- |
| Content width | 1200px / 75rem | `.shell` uses `min(75rem, viewport gutter)` |
| Desktop gutter | 2.5rem | Reduce to 1.25rem below 680px |
| Control target | 44px | Never reduce buttons, icon buttons, inputs, or pagination below this |
| Radius | 4px, 5px, 6px, 8px, 10px, pill | Use 5–6px controls, 8–10px cards, pill only for topics |
| Rule | 1px gold-alpha | Use a 2px gold segment only to mark a section heading |
| Shadow | `0 18px 44px rgb(0 0 0 / 45%)` | Navigation popover only |

## 5. Layout and Responsive Rules

| Range | Layout rule |
| --- | --- |
| Above 980px | Three-column header; article area plus 300px sidebar; two-column article grid with the first article spanning both columns. |
| 681–980px | Two-column header with native `details` menu; main and sidebar stack; sidebar sections form two columns. |
| 680px and below | 1.25rem page gutter; 70px header; one-column articles and sidebar; hero becomes bottom-aligned and uses a vertical legibility overlay. |

Use CSS Grid for the page shell and card layouts, Flexbox for aligned controls and compact lists, and `overflow-x: auto` for topic pills. Do not use absolute positioning for content layout; reserve it for decorative overlays and the mobile menu.

## 6. Pattern Library

### Header and navigation

- Height: 82px desktop, 70px small mobile.
- Desktop order: brand left, primary navigation centred, actions right.
- Active navigation: warm-white text plus a 2px inset gold underline.
- Mobile navigation: native `<details>` and `<summary>`; preserve keyboard and screen-reader behavior.
- Search and menu controls are 44px icon buttons with visible focus rings.

### Hero

- Minimum height: 390px desktop, 470px small mobile.
- Background: text-safe `blog-archive-hero.png`, with a left-to-right navy overlay on desktop and stronger bottom overlay on mobile.
- Copy limit: 11ch heading, 54ch supporting copy, and one gold-soft kicker.
- Never bake heading, navigation, or legal wording into the image.

### Topic bar

- Elevated navy surface with one bottom rule.
- Pill links have a 1px rule border and use gold only for active or hover state.
- Keep sorting text outside the scrollable topic list.

### Article card

- Rich-navy surface; 1px rule border; 10px radius.
- Standard media is 16:9; the lead article may use 2.25:1 only on desktop.
- Order: decorative image, category, linked serif title, excerpt, compact metadata.
- Marketing images are editorial promotion only; use empty `alt` when adjacent text supplies the meaning.

### Sidebar

- Desktop width: 300px with a left rule and 1.4rem inset.
- On tablet and below, stack under content with a top rule.
- Use short rule-underlined headings, not large display headings.

### Newsletter panel

- Gold border, 8px radius, restrained navy gradient.
- `newsletter-updates-illustration.png` may sit as a low-opacity decorative background detail only.
- Inputs and subscribe control remain real HTML with 44px minimum targets.

### Featured resource and recent posts

- Featured resource uses a rich-navy card and full-width primary action.
- Recent-post rows use a 76px × 58px thumbnail, compact title, and muted date.
- Do not use thumbnails as the only identifier of a post.

### Pagination and footer

- Pagination targets are 42px in the template; use 44px for new interactive controls when space permits.
- Active page is gold with deep-navy label.
- Footer returns to the deepest navy, with centred content after the 980px breakpoint.

## 7. Asset Rules

| Asset group | Use in this system | Restriction |
| --- | --- | --- |
| `backgrounds/blog-archive-hero.png` | Blog and resource hero behind HTML copy | Preserve the overlay and copy-safe side |
| `illustrations/newsletter-updates-illustration.png` | Low-opacity newsletter decoration | Never replace newsletter heading or input |
| `generated/marketing/illustrations/` | Article and editorial promotion imagery | Not product UI; empty `alt` with adjacent contextual copy |
| `logo/custodybuddy-wordmark-light.svg` | Dark-surface header and footer | Use meaningful `alt="CustodyBuddy"` when linked home |
| `generated/references/` | Internal source reference only | Do not use in public pages |

## 8. Accessibility and Content Rules

- Preserve the skip link and its visible-on-focus behavior.
- Maintain a 3px gold focus outline with 4px offset for links, inputs, buttons, and summaries.
- Use semantic landmarks: header, navigation, main, aside, footer, and labelled forms.
- Keep decorative and adjacent-context images at `alt=""`; use meaningful alt text only when the image conveys content not already expressed nearby.
- Do not use `#` placeholder links in a production page. Replace them with real destinations before publication.
- Retain `prefers-reduced-motion: reduce` for smooth scrolling and add it to any future motion.
- The template's desktop, tablet, and mobile layouts must be visually reviewed after content or artwork changes; static checks do not prove contrast over imagery or responsive behavior.

## 9. Implementation Guidance

This design system is documentation, not a second stylesheet. When the static template changes, update its `:root` tokens first and then update this document if a design decision changes.

1. Prefer existing token values over new raw hex, px, or rem values.
2. Add a new value only when it represents a durable design decision, not a one-off visual adjustment.
3. Keep application implementation separate from this asset repository.
4. Update `public/brand/asset-manifest.json` and the showcase when an asset changes; update this document when the visual rule changes.

## 10. Known Template Limits

- Navigation, search, forms, filters, pagination, and article links are static examples; they require real destinations and behavior in an application.
- The system documents one dark editorial theme only.
- The image overlays are part of legibility; any alternative hero art requires a new contrast review.
- No browser viewport validation was performed while writing this document.
