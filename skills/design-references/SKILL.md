---
name: design-references
description: Consult design-system references (colors, typography, spacing, components) inspired by well-known brands such as Apple, Stripe, Linear, Vercel, Notion, Spotify, Airbnb and others. Use when the user asks to build or restyle a UI "in the style of" a brand, wants a visual direction, or needs concrete design tokens to start from.
---

# Design References

Each brand has a `DESIGN.md` inside the plugin's `designs/` folder, at `${CLAUDE_PLUGIN_ROOT}/designs/<brand>/DESIGN.md`. Every file is an inspired interpretation of the brand's design language: color tokens, typography, spacing, radius, elevation and component patterns.

## Available brands

adobe, airbnb, anthropic, apple, asana, atlassian, bmw, cloudflare, cursor, duolingo, elevenlabs, google, linear, microsoft, netflix, notion, openai, perplexity, ramp, revolut, spotify, stripe, supabase, vercel

## How to use

1. Identify which brand(s) the user wants to reference. If they didn't name one, suggest 2-3 that fit the product (e.g. Linear or Vercel for dev tools, Airbnb or Spotify for consumer apps) and ask.
2. Read only the matching `DESIGN.md` file(s). Do not load all of them.
3. Translate the tokens into the user's stack (CSS variables, Tailwind config, theme object, SwiftUI, etc.) instead of copying the file verbatim.
4. These are inspirations, not official brand assets. Do not reproduce logos or trademarked artwork, and do not present the result as the brand's actual product.
5. For motion decisions on top of the visual direction, defer to the `animate` and `review-animations` skills.
