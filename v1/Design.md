> **Design Lock v1:** Finalized for the current Rangoon.Tech brand guide implementation. Treat this file as the source of truth for layout, breakpoints, buttons, typography, color, and theme behavior. Do not change it unless the brand system is intentionally revised.

## Overview

Rangoon.Tech's web presence is a premium bilingual brand guide for an experiential technology partner. The interface should feel practical, creative, reliable, and artifact-led. Brand assets, typography specimens, color rules, voice examples, imagery direction, and downloads are the primary objects on the page; UI chrome must stay quiet.

The system uses large surface shifts, precise typography, minimal borders, controlled interaction color, and strong imagery. It should not feel like a dense dashboard. It should feel like a guided brand system where each section has enough space for the content to be inspected and trusted.

**Key Characteristics:**

- Brand-artifact-first presentation; UI recedes so logos, colors, typography, and imagery can lead.
- Alternating full-width sections: Soft White and white for utility content, Midnight Teal for dark showcase moments.
- RTX-only color system. No non-brand colors in UI, themes, focus states, or decoration.
- Dark theme uses Midnight Teal (`--rtx-color-midnight-teal: #021A26`) as the main background, not black.
- Mint Teal is the primary action color; Sky Blue is the secondary link/action color.
- Bright Gold is reserved for rewards, premium campaign moments, and special highlights only.
- Typography is confident but restrained: Sora/Poppins for English, Masterpiece/OT fonts for Burmese and quote/logo roles.
- Large imagery moments show people, places, and technology working together.
- Cards stay flat with hairline borders; shadows are avoided.
- Responsive behavior preserves readable bilingual content and tappable controls across phone, tablet, desktop, and wide desktop.

## Colors

Only Rangoon.Tech colors may be used in the interface.

```css
:root {
  --rtx-color-midnight-teal: #021A26;
  --rtx-color-mint-teal: #29DDB9;
  --rtx-color-sky-blue: #0272A7;
  --rtx-color-almost-black: #000C12;
  --rtx-color-soft-white: #F7FBFA;
  --rtx-color-bright-gold: #FFD700;
}
```

### Brand & Accent

- **Midnight Teal** (`--rtx-color-midnight-teal` — #021A26): The core brand surface. Used for hero sections, dark theme background, logo showcase surfaces, dark navigation, and premium brand moments.
- **Mint Teal** (`--rtx-color-mint-teal` — #29DDB9): The primary action color. Used for main CTAs, selected high-priority controls, active states, and key brand highlights.
- **Sky Blue** (`--rtx-color-sky-blue` — #0272A7): The secondary action color. Used for links, secondary actions, technical metadata, and supporting digital cues on light surfaces. Do not use Sky Blue as normal text on Midnight Teal.
- **Bright Gold** (`--rtx-color-bright-gold` — #FFD700): A special-use accent for rewards, premium moments, campaign mechanics, and celebration states. It must not be used as routine UI color.

### Surface

- **Soft White** (`--rtx-color-soft-white` — #F7FBFA): Default light canvas. Used for the page background, quiet sections, footer areas, and utility content.
- **White** (`#ffffff`): Card and utility surface in light theme. White is allowed only as a neutral surface, not as a new brand color.
- **Midnight Teal** (`--rtx-color-midnight-teal` — #021A26): Default dark canvas and dark theme page background.
- **Almost Black** (`--rtx-color-almost-black` — #000C12): Deep contrast surface for small utility regions, code-like examples, dense panels, and text on light surfaces. It must not replace Midnight Teal as the main dark background.
- **Translucent Chip Surface** (`--rtx-surface-chip-translucent`): A translucent utility surface for controls placed over imagery, dark showcase tiles, or floating bars. It must be made from RTX colors only.

Light theme tokens:

```css
:root,
[data-theme="light"] {
  --rtx-theme-canvas: var(--rtx-color-soft-white);
  --rtx-theme-surface: #ffffff;
  --rtx-theme-surface-alt: var(--rtx-color-soft-white);
  --rtx-theme-ink: var(--rtx-color-almost-black);
  --rtx-theme-ink-muted: rgba(0, 12, 18, 0.72);
  --rtx-theme-ink-muted-subtle: rgba(0, 12, 18, 0.56);
  --rtx-theme-muted: rgba(2, 26, 38, 0.72);
  --rtx-theme-hairline: rgba(2, 26, 38, 0.14);
  --rtx-theme-action: var(--rtx-color-mint-teal);
  --rtx-theme-link: var(--rtx-color-sky-blue);
}
```

Dark theme tokens:

```css
[data-theme="dark"] {
  --rtx-theme-canvas: var(--rtx-color-midnight-teal);
  --rtx-theme-surface: var(--rtx-color-midnight-teal);
  --rtx-theme-surface-alt: var(--rtx-color-almost-black);
  --rtx-theme-ink: var(--rtx-color-soft-white);
  --rtx-theme-ink-muted: rgba(247, 251, 250, 0.74);
  --rtx-theme-ink-muted-subtle: rgba(247, 251, 250, 0.56);
  --rtx-theme-muted: rgba(247, 251, 250, 0.74);
  --rtx-theme-hairline: rgba(247, 251, 250, 0.16);
  --rtx-theme-action: var(--rtx-color-mint-teal);
  --rtx-theme-link: var(--rtx-color-mint-teal);
}
```

Translucent chip tokens:

```css
:root,
[data-theme="light"] {
  --rtx-surface-chip-translucent: rgba(247, 251, 250, 0.72);
  --rtx-surface-chip-translucent-strong: rgba(247, 251, 250, 0.88);
}

[data-theme="dark"] {
  --rtx-surface-chip-translucent: rgba(2, 26, 38, 0.72);
  --rtx-surface-chip-translucent-strong: rgba(0, 12, 18, 0.72);
}
```

Usage rules:

- Use translucent chips for image carousel arrows, close buttons, compact floating controls, and over-image utility actions.
- Pair with `backdrop-filter: blur(12px);` where browser support allows.
- Use Soft White or Almost Black icon/text color based on the image underneath.
- Do not use translucent chips for normal cards or large content containers.

### Text

- **Primary Text on Light**: Almost Black (#000C12).
- **Ink Muted on Light**: Almost Black at 72% opacity for secondary body, descriptions, and supporting metadata.
- **Ink Muted Subtle on Light**: Almost Black at 56% opacity for disabled text, timestamps, and low-priority metadata. Do not use below 14px without checking contrast.
- **Muted Text on Light**: Midnight Teal at reduced opacity.
- **Primary Text on Dark**: Soft White (#F7FBFA).
- **Ink Muted on Dark**: Soft White at 74% opacity for secondary body, descriptions, and supporting metadata.
- **Ink Muted Subtle on Dark**: Soft White at 56% opacity for low-priority metadata and disabled text. Do not use for long body copy.
- **Muted Text on Dark**: Soft White at reduced opacity.
- **Interactive Text on Light**: Sky Blue or Midnight Teal depending on hierarchy.
- **Interactive Text on Dark**: Mint Teal. Sky Blue must not be used for normal-size text on Midnight Teal because the contrast is too low.
- **Minimum Normal Text Contrast**: Use pairings that meet at least 4.5:1 for 17px body, 14px UI text, and 13px captions.
- **Minimum Large Text Contrast**: Large display text may use 3:1 minimum, but RTX default pairings should still target 4.5:1 or higher.

### Hairlines & Borders

- Light theme hairlines use Midnight Teal at low opacity.
- Dark theme hairlines use Soft White at low opacity.
- Borders should create structure without making the interface feel boxed-in.
- Use hairlines for cards, utility rows, tables, filters, and nav separators.
- Avoid heavy outlines except for selected states.

### Brand Gradient

Gradients are brand assets, not default UI atmosphere.

Current project gradients:

- **Primary Gradient**: Midnight Teal → Sky Blue → Mint Teal.
- **Dark Gradient**: Almost Black → Midnight Teal → Sky Blue.
- **Experience Gradient**: Sky Blue → Mint Teal → Bright Gold.

Readability audit:

| Gradient | Light Theme Use | Dark Theme Use | Text Safety |
| --- | --- | --- | --- |
| Primary Gradient | Brand swatch, campaign cover, visual accent | Brand swatch or accent only | Not safe for normal text across the full gradient. Soft White works on Midnight/Sky but fails on Mint; Almost Black works on Mint but not on Midnight/Sky. |
| Dark Gradient | Premium dark visual tile or cover | Best gradient option for dark showcase moments | Safe with Soft White text across the stops. Use for short headlines or cover moments only. |
| Experience Gradient | Reward/campaign visual, not routine UI | Avoid as dark-theme background | Not safe for normal text across the full gradient. Gold and Mint require dark text; Sky requires light text for best readability. |

Usage rules:

- Show gradients in the color-system section as documented brand tools.
- Use gradients only for special brand moments, campaign covers, proposal covers, or generated visual direction.
- Do not place long text on bright gradients.
- Do not place normal text on Sky Blue → Midnight Teal or other low-contrast gradient regions without a readable solid overlay.
- Do not use gradients as routine section backgrounds.
- If text must sit on Primary Gradient or Experience Gradient, place it inside a solid or translucent RTX surface chip/card rather than directly on the gradient.
- For dark theme, prefer solid Midnight Teal over gradients. If a gradient is required, use Dark Gradient with Soft White text.

## Typography

### Font Family

- **English Display / Heading**: `Sora, system-ui, sans-serif`.
- **English Body / UI**: `Poppins, system-ui, sans-serif`.
- **Burmese Display**: `Masterpiece Daung Round, system-ui, sans-serif`.
- **Burmese Body**: `Masterpiece Uni Sans, system-ui, sans-serif`.
- **Logo-style Burmese**: `OT04 Blox, system-ui, sans-serif`.
- **Quote-style Supporting Text**: `OT21_TwelLet, system-ui, sans-serif`.

Font role rules:

- Use Sora for short, confident English headlines.
- Use Poppins Regular for readable English body text.
- Use Poppins Medium sparingly for supporting emphasis.
- Use Masterpiece Daung Round for Burmese display text.
- Use Masterpiece Uni Sans for Burmese paragraphs and UI copy.
- Use OT04 Blox only for logo-style display moments.
- Use OT21 TwelLet only for quote-style supporting text.

### Hierarchy

| Token | Size | Weight | Line Height | Use |
| --- | ---: | ---: | ---: | --- |
| `rtx-display-xl` | 72px | 700 | 1.10 | Hero title and major brand moments |
| `rtx-display` | 56px | 600 | 1.12 | Large section statements |
| `rtx-heading-1` | 40px | 600 | 1.20 | Main section titles |
| `rtx-heading-2` | 28px | 600 | 1.28 | Subsection titles |
| `rtx-body` | 17px | 400 | 1.47 | Editorial body and section intro copy |
| `rtx-ui` | 14px | 400 / 600 | 1.35 | Buttons, labels, table text |
| `rtx-caption` | 13px | 400 / 600 | 1.45 | Metadata and small labels |
| `rtx-mm-display-xl` | 64px | 700 | 1.50 | Burmese hero title |
| `rtx-mm-display` | 48px | 700 | 1.55 | Large Burmese statements |
| `rtx-mm-heading-1` | 36px | 700 | 1.60 | Burmese section titles |
| `rtx-mm-heading-2` | 26px | 700 | 1.60 | Burmese subsection titles |
| `rtx-mm-body` | 17px | 400 | 1.85 | Burmese body text |
| `rtx-mm-caption` | 13px | 400 | 1.65 | Burmese metadata and labels |

### Principles

- Use `600` for most English headings; reserve `700` for hero-scale or major brand moments.
- Body copy should read clearly at 16-17px. Prefer 17px in editorial sections.
- Do not use weight `500` as a default emphasis layer.
- Avoid excessive uppercase labels.
- Keep English headings tight and confident without crowding.
- Keep Burmese text more open than English. Do not force Burmese line-height into English proportions.
- Do not use Thin or ExtraLight for normal content.
- Maintain bilingual readability before visual compactness.

### Note on Font Substitutes

The brand guide uses local font files from the current project assets. If a font fails to load, fallback to `system-ui, sans-serif` while preserving the same size, weight, and line-height tokens.

Do not replace the brand type system with SF Pro, Inter, Roboto, or another product UI font unless the brand system is officially revised.

## Layout

### Spacing System

The layout uses an 8px base rhythm with smaller values only for tight typographic or control adjustments.

- `4px`: micro adjustment.
- `8px`: tight gap.
- `12px`: compact control gap.
- `16px`: small content gap.
- `24px`: card padding.
- `32px`: block spacing.
- `48px`: section grouping.
- `80px`: desktop section padding.

### Grid & Container

- **Standard container**: `min(1180px, calc(100% - 32px))`.
- **Text container**: `min(840px, calc(100% - 32px))`.
- **Visual showcase container**: `min(1440px, calc(100% - 32px))`.
- **Utility grid**: 2-3 columns on desktop, 1 column on phone.
- **Logo grid**: 2 columns on desktop, 1 column on phone.
- **Imagery grid**: mixed-size mosaic on desktop, lead image plus stacked tiles on mobile.

### Whitespace Philosophy

Whitespace is the presentation surface for the brand artifacts. Logos, typography specimens, color swatches, and imagery need enough room to be inspected.

Rules:

- Keep at least 40px between major visual assets and nearby explanatory text.
- Do not stretch paragraphs across wide screens.
- Use extra desktop width for imagery, logos, and brand examples.
- Let section surface changes act as dividers.
- Avoid unnecessary nested boxes.

## Elevation & Depth

| Level | Treatment | Use |
| --- | --- | --- |
| Flat | No shadow, no border | Full-width sections, hero, footer, large showcase areas |
| Hairline | 1px low-opacity RTX border | Cards, tables, filters, utility rows, navigation separators |
| Frosted | Translucent RTX surface with backdrop blur | Sticky sub-nav or floating utility bars |
| Selected | 2px RTX action border or clear filled state | Selected filters, active options |

Cards, buttons, text, and sections should not use decorative shadows. Depth comes from surface changes, spacing, scale, and imagery.

### Decorative Depth

Decorative depth must come from brand assets and imagery, not generic visual effects.

Allowed:

- Crisp Burst Mark as a visible brand artifact.
- Large photography or generated imagery.
- Subtle translucent controls over images.
- Backdrop-filter blur on frosted navigation, translucent over-image controls, and floating utility bars. This creates a floating-over-content effect that is functional, not decorative.
- Brand gradients only where documented as brand artifacts or campaign moments.

Avoid:

- Random glow effects.
- Non-brand gradient backgrounds.
- Heavy shadows.
- Decorative blobs or orbs.
- Pure black page backgrounds in dark mode.

## Shapes

### Border Radius Scale

| Token | Value | Use |
| --- | ---: | --- |
| `rtx-radius-none` | 0px | Full-width section tiles and surface transitions |
| `rtx-radius-sm` | 8px | Utility buttons, compact cards, inline image corners |
| `rtx-radius-lg` | 18px | Larger asset cards, logo cards, imagery cards |
| `rtx-radius-pill` | 9999px | Primary CTAs, selected filters, search/filter inputs |
| `rtx-radius-full` | 9999px / 50% | Circular image controls and icon buttons |

Rules:

- Do not round full-width sections.
- Do not use many intermediate radii.
- Use pill shape only for action or selection grammar.
- Keep utility controls compact and predictable.

### Photography Geometry

- Hero imagery and showcase imagery should use wide, immersive crops.
- Logo assets need clear space and centered presentation.
- Imagery grids should mix large lead tiles and smaller supporting tiles.
- Use 18px radius for image cards only when the image is inside a utility grid.
- Full-bleed visual sections should remain rectangular.
- Avoid making all images the same size when one image should clearly lead.

## Components

### Top Navigation

The navigation is sticky, thin, and quiet.

Structure:

- Brand mark and brand label.
- Section navigation.
- Language toggle.
- Optional export or download action.

Surface:

- Light mode: Soft White or white with low-opacity Midnight Teal hairline.
- Dark mode: Midnight Teal with Soft White text.
- Frosted sub-nav may use translucent Soft White on light mode and translucent Midnight Teal on dark mode.

Rules:

- Keep nav labels compact.
- Avoid large filled nav pills.
- Hide secondary nav links on smaller devices.
- Preserve brand mark visibility at every breakpoint.

### Buttons

**Primary Button**

- Fill: Mint Teal.
- Text: Almost Black or Midnight Teal.
- Shape: pill.
- Use: main action, selected high-priority command.

**Secondary Button**

- Fill: transparent or surface color.
- Text: Sky Blue on light theme, Mint Teal on dark theme.
- Border: action color or low-opacity hairline.
- Shape: pill.

**Dark Utility Button**

- Fill: Midnight Teal or Almost Black.
- Text: Soft White.
- Radius: 8px.
- Use: compact header, export, or utility actions.

**Icon Button**

- Size: at least 40px where practical.
- Shape: 8px radius or full circle.
- Border: low-opacity RTX hairline.
- Use: copy, download, image navigation, external links.

Interaction:

- Active state may use `transform: scale(0.97);`
- Focus state must use RTX colors only.
- Hover states must not introduce non-RTX colors.

### Cards & Containers

**Asset Card**

- Surface: white on light theme, Midnight Teal or Almost Black on dark theme.
- Border: hairline.
- Radius: 18px maximum.
- Shadow: none.
- Use: logo assets, imagery groups, downloadable brand artifacts.

**Utility Card**

- Surface: white or Soft White on light theme.
- Border: hairline.
- Radius: 8px.
- Padding: 24px.
- Use: strategy, overview, rules, voice examples, token lists.

**Showcase Tile**

- Surface: Midnight Teal, Soft White, or white.
- Radius: 0 when full-width.
- Use: hero, logo showcase, imagery moments.

**Selected Filter Chip**

- Shape: pill.
- Selected state: Mint Teal fill or 2px Mint Teal border.
- Use: logo filters, image categories, content filters.

### Inputs & Forms

Search and filter inputs should match the action grammar.

- Shape: pill.
- Surface: white on light theme, Midnight Teal or Almost Black on dark theme.
- Border: RTX hairline.
- Text: theme ink.
- Focus: Mint Teal or Sky Blue using RTX colors only.
- Height: at least 40px.

### Footer

The footer is dense but quiet.

- Surface: Soft White in light mode.
- Surface: Midnight Teal in dark mode.
- Text: muted theme text.
- Links: Sky Blue on light mode, Mint Teal on dark mode.
- Use compact rows or columns.
- Avoid large decorative footer cards.

## Do's and Don'ts

### Do

- Use only Rangoon.Tech colors.
- Use Midnight Teal as the dark theme background.
- Use Mint Teal for primary actions.
- Use Sky Blue for secondary links/actions on light surfaces.
- Keep Gold special.
- Keep cards flat.
- Use hairlines for structure.
- Give logos and imagery enough space.
- Keep typography confident and restrained.
- Preserve Burmese readability with generous line-height.
- Let section surface changes create rhythm.

### Don't

- Do not use black as the dark theme page background.
- Do not introduce non-RTX colors.
- Do not use gold as routine UI.
- Do not add decorative card shadows.
- Do not overuse filled badges.
- Do not make every section look like a dashboard panel.
- Do not use gradients as default section backgrounds.
- Do not recreate official logos with live text.
- Do not crowd imagery with metadata.
- Do not force Burmese typography into English spacing.

## Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
| --- | ---: | --- |
| Small phone | `<= 419px` | Single-column layout. Hide secondary nav links. Keep brand mark, language toggle, and one essential action. Hero title uses compact display size. Cards and tables stack. |
| Phone | `420px - 640px` | Single-column sections. Reduce section padding while preserving breathing room. Logo cards, color cards, typography rows, and downloads stack. Imagery shows one large lead image followed by smaller tiles. |
| Large phone | `641px - 735px` | Keep single-column reading flow. Allow wider image crops. Filters may wrap or scroll horizontally. Avoid cramped two-column cards. |
| Tablet portrait | `736px - 833px` | Header may collapse long nav. Use two-column layouts only where content remains readable. Typography specimens may still stack English and Burmese. |
| Tablet landscape | `834px - 1023px` | Restore more nav links. Use two-column strategy and logo grids. Imagery may use a mixed mosaic. Section headers can use kicker/title split layout. |
| Desktop | `1024px - 1439px` | Use standard centered container. Larger hero, 2-3 column utility grids, stronger logo showcase, richer imagery layout. |
| Wide desktop | `>= 1440px` | Keep content constrained. Do not stretch paragraphs. Use extra width for imagery, logos, and brand artifacts. |

### Touch Targets

- Keep primary buttons and icon buttons at least 40px tall where practical.
- Image carousel controls must remain tappable on touch devices.
- Filter chips must wrap cleanly or scroll horizontally without clipping.
- Language controls must remain readable in English and Burmese.

### Collapsing Strategy

- Collapse secondary navigation before shrinking the brand mark.
- Stack section headers on mobile.
- Stack English and Burmese typography examples on mobile and tablet portrait.
- Convert dense utility rows into stacked rows on small screens.
- Keep primary actions visible.

### Image Behavior

- Mobile: one lead image followed by stacked supporting images.
- Tablet: mixed layout only when captions and controls remain readable.
- Desktop: mosaic layout with clear hierarchy.
- Wide desktop: expand image presentation, not paragraph length.
- Avoid cropped images that hide the human action or technology object.

## Iteration Guide

Implementation order:

1. Define RTX color and theme tokens.
2. Refactor header and hero around Midnight Teal, Soft White, and Mint Teal.
3. Normalize buttons, chips, icon actions, and focus states.
4. Restyle cards and repeated lists with softer hairlines.
5. Promote logo and imagery sections into larger showcase moments.
6. Validate responsive behavior across small phone, phone, tablet, desktop, and wide desktop.

Review checklist:

- The page uses only RTX colors.
- Dark mode background is Midnight Teal.
- Gold appears only as a special-use accent.
- Typography is readable in English and Burmese.
- Imagery shows people, places, and technology together.
- UI controls do not compete with brand artifacts.
- Cards remain flat.
- Mobile layouts do not overflow.

## Known Gaps

- Final dark theme implementation needs visual testing across all sections.
- Burmese line-height should be verified with real production copy, not only short specimen strings.
- Imagery metadata links currently include placeholders and should be finalized.
- Gradient usage needs strict review so gradients stay as brand artifacts instead of routine UI backgrounds.
- Logo showcase spacing should be checked against approved clear-space rules.
- Accessibility contrast should be tested for Mint Teal text on Midnight Teal and Sky Blue on dark surfaces.
