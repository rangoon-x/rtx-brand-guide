# Rangoon.Tech Brand CDN v1

This folder is the CDN-ready asset package for the Rangoon.Tech Brand Guide v1.

## Contents

- `Design.md` - locked v1 source of truth for layout, breakpoints, buttons, typography, color, and theme behavior.
- `manifest.json` - stable asset map for app integration.
- `styles/fonts.css` - CDN font-face declarations.
- `styles/tokens.css` - CSS custom properties for brand colors and theme tokens.
- `tokens/colors.json` - machine-readable color tokens.
- `assets/Logos/` - logo and mark files.
- `assets/English Font/` - English brand fonts.
- `assets/Burmese Font/` - Burmese brand fonts.
- `assets/07imagery/HQ/` - high-quality PNG imagery, used by default.
- `assets/07imagery/LQ/` - low-quality WebP imagery, used for data-saver or very slow networks.
- `assets/Colors/` - color reference image.

## CDN Usage

Use one immutable base URL per version:

```txt
https://cdn.rangoon.tech/brand/v1
```

The app should read this from an environment variable:

```txt
VITE_RTX_CDN_BASE=https://cdn.rangoon.tech/brand/v1
```

Never hardcode a provider-specific URL throughout the app. Keep all asset paths relative to the CDN base.

## Imagery Quality

Use HQ imagery by default. LQ imagery is only a network fallback for data-saver or very slow effective connection types such as `slow-2g` and `2g`.

Most basic CDNs serve the exact file requested by the app; they do not automatically choose between `HQ` and `LQ`. Automatic quality selection requires either app logic or an image CDN/optimizer such as Cloudflare Images, ImageKit, Imgix, or a similar service.

The brand guide app supports a query override:

```txt
?quality=auto
?quality=hq
?quality=lq
```

`auto` is the default behavior: HQ unless data-saver or very slow network is detected.

## Release Rule

After v1 is published, treat it as immutable. Fixes that change file content should ship as `v1.0.1` or `v2`, depending on how the CDN is configured.
