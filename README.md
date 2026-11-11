# RSI Industrial

A dark, RSI-inspired Home Assistant theme based on the Multi-Function Displays (MFDs) in **Star Citizen**.

The visual direction uses graphite and blue-gray surfaces, brighter illuminated aerospace-blue controls, cyan instrumentation accents, restrained amber highlights, and readable technical text. It is designed as a responsive-friendly global theme for phones, tablets, and desktop displays.

## Features

- Deep graphite background and blue-gray card surfaces
- Brighter illuminated blue primary buttons, switches, sliders, and controls
- Oxanium typography across the interface (requires card-mod and an internet connection to Google Fonts)
- Soft aerospace-blue edge glow on standard Button cards when card-mod is installed
- Cyan instrumentation accents for navigation and active status indicators
- Amber highlights for attention and illuminated equipment states
- Muted steel-blue secondary text and dividers
- Dark-mode palette

> **Project status:** Early development (v0.5). The global palette, brighter blue controls, and Oxanium typography prototype are in place. The font is loaded from Google Fonts; Home Assistant clients need internet access and card-mod installed.

## Installation with HACS

1. Open **HACS** in Home Assistant.
2. Open the three-dot menu and select **Custom repositories**.
3. Add `https://github.com/anazario93/ha-rsi-theme` and choose **Theme** as the category.
4. Add the repository, find **RSI Industrial**, and download it.
5. If themes are not already enabled, add the following to your existing `configuration.yaml`:

   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```

   If you already have a `frontend:` section, add `themes:` beneath it rather than creating a duplicate section.
6. Run **Developer Tools → Actions → frontend.reload_themes** (or restart Home Assistant).
7. Select **RSI Industrial** in your Home Assistant user profile.

## Typography: Oxanium

The theme uses [Oxanium](https://fonts.google.com/specimen/Oxanium), designed by Severin Meyer and distributed under the SIL Open Font License 1.1. The font is loaded from Google Fonts rather than bundled in this repository. This avoids redistributing font binaries while preserving the open license; clients need internet access to retrieve the font. The font is applied to the overall Home Assistant interface through theme typography variables and card-mod root styling. The repository includes the font license in `OFL-Oxanium.txt`.

## Optional: MFD button glow with card-mod

The illuminated edge glow on standard Home Assistant Button cards uses [card-mod](https://github.com/thomasloven/lovelace-card-mod). Install card-mod through HACS and ensure its dashboard resource is loaded. The theme then applies a restrained blue border and layered glow to standard Button cards only; other cards keep their existing shadow treatment. Card-mod 4.2.0 is the current compatible release line for Home Assistant 2026.2 and newer.

## Manual installation

1. Download `themes/rsi_industrial.yaml`.
2. Place it in the `themes/` directory in your Home Assistant configuration folder.
3. Ensure the `frontend:` configuration above is present.
4. Reload themes and select **RSI Industrial** in your profile.

## Color palette

| Role | Color | Hex |
|---|---|---|
| Main background | Graphite | `#101719` |
| Panels and cards | Blue-gray | `#1C2A31` |
| Primary controls | Brighter illuminated aerospace blue | `#20A9E8` |
| Instrumentation accents | Cyan | `#39D9E9` |
| Attention / selected accent | Amber | `#F0C85A` |
| Primary text | Display white | `#D5E5E7` |
| Secondary text | Steel blue-gray | `#91AEB4` |

## Compatibility and notes

- This repository contains a Home Assistant **theme**, not a custom integration or dashboard card.
- The theme does not change dashboard navigation, entity IDs, actions, or visibility rules.
- Standard Home Assistant cards will inherit supported theme variables. Fine-grained MFD button styling may require a separate styling solution such as card-mod.
- The theme is dark-only by design.

## Feedback

Issues and suggestions are welcome. Please include your Home Assistant version, a screenshot, and the device/display size when reporting visual issues.

## Credits

Inspired by the industrial cockpit MFD visual language of RSI ships in *Star Citizen*. This is an independent community theme and is not affiliated with or endorsed by Cloud Imperium Games or Roberts Space Industries.
