# Step Labs Shopify assessment

Two configurable sections built from the Step Labs Figma design, a split hero and a results stats section, on the Horizon 4.2.0 theme.

- Store: https://fernando-step-labs-assessment.myshopify.com/

## Files

| Section | Files |
|---|---|
| Split hero | `sections/hero-split.liquid`, `assets/hero-split-*.svg` |
| Results stats | `sections/results-stats.liquid`, `blocks/_results-group.liquid`, `blocks/_results-stat.liquid`, `assets/results-stats-arrow.svg` |
| Home page | `templates/index.json` (Horizon's demo content removed) |

## Sections

**Split hero.** Settings for the image, colors, fonts and height. Blocks: rating, heading, text, buttons, note and feature. Blocks can be added, removed and reordered, and neighboring feature blocks render as one row.

**Results stats.** Settings for the image, heading, button, footnotes, colors, fonts and an optional anchor ID (the hero's "How It Works" links to `#results`). Stats are nested blocks inside stat groups, so the editor shows them as a tree.

Both sections load their own fonts, scope their colors to the section instance, and work alone, together, reordered or duplicated.

## Design fidelity

At 1440px width every element sits close to its Figma position. The design font, Suji Onsite, isn't available in Shopify, so the sections default to Schibsted Grotesk, the closest match I measured in Shopify's font library.

Figma only has desktop frames, so the layouts below 1440px are my own: stacked on mobile, side by side from 750px (hero) and 990px (results).

## Development

```sh
shopify theme dev --environment development
shopify theme check
```

`shopify.theme.toml` points these commands at the assessment theme (#190449516829), which is the published theme, so `theme dev` and `theme push` edit the live store.

## Known limitations

- The Figma hero photo is only 720px wide, so it looks soft on large screens.