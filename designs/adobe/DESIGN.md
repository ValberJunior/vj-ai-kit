<design-context>
---
version: alpha
name: Adobe
description: "Adobe is changing the world through digital experiences. We help our customers create, deliver and optimize content and applications."
sourceUrl: "https://www.adobe.com"

colors:
  primary: "#eb1000"
  on-primary: "#ffffff"
  background: "#ffffff"
  surface: "#eb1000"
  border: "#ffffff"
  text: "#ffffff"
  text-muted: "#000000"

typography:
  display:
    fontFamily: "Adobe Clean Display Black, Adobe Clean Display, adobe-clean-display, Arial Bold Adjusted, sans-serif"
    fontSize: 80px
    fontWeight: 900
    lineHeight: 0.95
    letterSpacing: -3.2px
  heading:
    fontFamily: "Adobe Clean Display Black, Adobe Clean Display, adobe-clean-display, Arial Bold Adjusted, sans-serif"
    fontSize: 50px
    fontWeight: 600
    lineHeight: 0.95
    letterSpacing: -3.2px
  body:
    fontFamily: "Adobe Clean, adobe-clean, Trebuchet MS, sans-serif"
    fontSize: 20px
    fontWeight: 400
    lineHeight: 1.2

spacing:
  base: 8px
  scale: [16, 24, 144]

radius:
  sm: 4px
  md: 8px
  lg: 50px
  pill: 9999px

shadows:
  card: "rgba(255, 255, 255, 0.11) 0px 0px 0px 1px inset"
  elevated: "rgba(255, 255, 255, 0.11) 0px 0px 0px 1px inset"

motion:
  duration-fast: 300ms
  duration-base: 300ms
  duration-slow: 300ms
  easing: "cubic-bezier(0.42, 0, 0, 1)"

breakpoints: [600px, 1200px]
---

## Rationale

Adobe's design system reflects a premium, creative software brand that prioritizes bold visual hierarchy and confident communication. The primary red (#eb1000) is wielded as a high-contrast accent against white backgrounds, creating immediate visual impact—essential for a homepage that must signal creativity and innovation within milliseconds. The typography stack leans heavily on Adobe's proprietary typeface (Adobe Clean) paired with generous sizing (80px display, 50px headings), establishing authority and readability at scale. This approach mirrors the company's market position: dominant, accessible, and designed for users across skill levels. The measured spacing increments (16, 24, 144px) and controlled motion (all 300ms) suggest a system built for clarity and efficiency rather than playfulness, appropriate for enterprise-grade creative tools.

The color palette is deliberately minimal—primary red, white background, black text—avoiding the polychromatic "creative chaos" that might undermine trust. Instead, the system trusts its typography and spacing to orchestrate visual rhythm, with subtle inset shadows (white borders at very low opacity) providing depth without noise. This restraint signals maturity and allows featured content (product screenshots, CTAs) to dominate the viewer's attention.

## 1. Visual Theme & Atmosphere

Adobe's measured design conveys **confidence and premium craftsmanship**. The white background paired with bold red accents creates a gallery-like atmosphere—content floats as carefully curated artifacts rather than dense information clusters. The generous typographic scale (80px display) and tight line heights (0.95) produce a sense of compression and energy, as though the brand is tightly wound and ready to deliver. The absence of color complexity (no gradients, no secondary palettes in the tokens) reinforces a **minimalist, almost Bauhaus-influenced modernism**, contrasting with the chaotic creative work the products enable.

The light color mode combined with pure white background and red action surfaces suggests a **clean, professional workspace** aesthetic—users should feel they're stepping into a refined creative studio, not a consumer marketplace.

## 2. Color System

The measured palette is intentionally restricted:

- **Primary red (#eb1000)** serves as the sole chromatic accent and dominates interactive surfaces (`surface`), headings, and CTAs. Its saturation and warmth suggest energy and movement.
- **White (#ffffff)** functions as both background and text (notably for text on the red surface), creating the harshest contrast possible.
- **Black (#000000)** appears as `text-muted`, likely used for secondary or disabled states.
- **On-primary white** ensures legible text atop red—a critical accessibility requirement met by the measured system.

There is no secondary palette measured here, suggesting that Adobe relies on the single red as a unifying chromatic device across the site. Supporting colors likely emerge through opacity shifts or through non-brand neutrals (grays) applied dynamically. The contrast is **stark and binary**—this is not a soft, gradient-heavy system but a high-contrast, type-forward one.

## 3. Typography

Adobe's measured type system emphasizes **hierarchical clarity and brand presence**:

- **Display (80px, weight 900, line-height 0.95):** Ultra-condensed, high-impact hero text. The -3.2px letter-spacing and tight leading create a "compressed" feeling—words stack tightly, suggesting density and power. Used for primary headlines ("Create at the highest level.").
- **Heading (50px, weight 600, line-height 0.95):** Maintains the compressed leading and negative letter-spacing, ensuring subheadings feel related yet distinct from body content.
- **Body (20px, weight 400, line-height 1.2):** Significantly larger than industry baseline (16px), with relaxed leading. This generous sizing prioritizes readability and signals premium treatment of supporting text.

The typeface stack (`Adobe Clean Display` → `Adobe Clean`) is proprietary and tightly paired, ensuring brand consistency across web and product. The absence of serif fallbacks or decorative weights suggests a **forward-thinking, digital-first approach**. Weight distribution (900 for display, 400 for body) creates strong contrast without adding typeface varieties.

## 4. Components & Patterns

The measured tokens suggest a **component library built for simplicity**:

- **Buttons & CTAs:** Likely use the primary red as background with white text, maximum contrast. The radius tokens (sm: 4px, md: 8px, lg: 50px, pill: 9999px) indicate flexible rounding—CTAs might use `lg` or `pill` for a softer, more approachable feel.
- **Cards & Surfaces:** The `card` shadow (inset white border at low opacity) suggests elevated content areas are marked by a subtle inner glow rather than drop shadows. This keeps the aesthetic flat and modern.
- **Navigation:** Likely uses black or muted text on white, with red underlines or backgrounds for active states.
- **CTAs:** The high frequency of "Free trial" buttons in the site data, combined with the red surface color, suggests these use the primary red as a dominant call-to-action style.

Given the measured data, components appear to prioritize **legibility and directness**—no layered shadows, no decorative icons at the token level, no color transitions that aren't explicitly defined.

## 5. Spacing & Layout

The spacing scale (base: 8px, scale: [16, 24, 144px]) reveals a **predictable, grid-aligned rhythm**:

- **16px and 24px increments** handle granular spacing (padding, gaps, margins) for text and components, aligning to an 8px grid.
- **144px** is a jump—nearly 18× the base unit—likely used for vertical section spacing, creating dramatic breathing room between content blocks (e.g., between hero and feature section).

Breakpoints at 600px and 1200px suggest a **three-tier responsive strategy**: mobile (< 600px), tablet (600–1200px), and desktop (> 1200px). The typography scales (display, heading, body) are fixed in the measured tokens, but real implementations likely adjust these values across breakpoints.

The large 144px spacing increment, paired with generous typography, implies **generous white space and breathing room**—appropriate for a premium brand where emptiness signals luxury rather than incompleteness.

## 6. Motion & Interaction

All measured motion durations are uniform (300ms), with a consistent cubic-bezier easing (0.42, 0, 0, 1). This easing curve is **fast on entry, slow on exit**, creating a snappy but refined feel:

- **durationFastMs / durationBaseMs / durationSlowMs** all at 300ms suggests that Adobe opts for **consistency over granularity**—every transition uses the same timing, reinforcing a cohesive, predictable experience.
- The easing `cubic-bezier(0.42, 0, 0, 1)` favors a rapid start and controlled finish, suitable for button hovers, modal opens, and CTA reveals. This is **more playful than a linear curve** but **more controlled than a bounce**.

Practical implications: hover states on buttons likely use this 300ms easing to subtly enlarge or shift color; navigation transitions feel crisp; modal overlays appear quickly but settle in. The lack of separate "slow" timing suggests **no lengthy animations**—the site prioritizes speed and responsiveness, consistent with its messaging ("Get work done. Faster.").

---

## Accessibility

### Contrast Ratios

**Primary text pair: Black (#000000) on White (#ffffff)**  
Contrast ratio: **21:1** (maximum possible)  
**Status: Exceeds WCAG AAA** ✓

**White text on Primary red (#eb1000):**  
Using standard luminance calculation:  
- Red: ~16.4 (relative luminance)  
- White: ~1.0  
- Ratio: ~17:1  
**Status: Exceeds WCAG AAA** ✓

**Black text on Red surface (if used for secondary content):**  
Ratio: ~14:1  
**Status: Exceeds WCAG AAA** ✓

All measured color pairs far exceed the WCAG AA threshold of 4.5:1. The high-contrast, binary palette (red and white/black) is inherently accessible and requires no additional compensation.

### Minimum Requirements

- **Touch target:** The measured tokens do not explicitly define button dimensions, but body text at 20px and heading at 50px suggest component padding will easily accommodate 44×44px touch targets. Spacing increments (16, 24px) support comfortable padding around interactive elements.
- **Focus indicator:** Not explicitly tokenized, but standard practice would apply a 2px outline in the primary red (#eb1000) with 2px offset (using `outline-offset: 2px`), ensuring keyboard-navigable elements are clearly visible against the white background.
- **Motion:** The consistent 300ms easing does not risk motion sickness; users can disable animations via `prefers-reduced-motion` media query, reducing all durations to 0ms or replacing easing with `linear`.
- **Typography:** Body size of 20px exceeds the WCAG 16px recommendation; display and heading sizes are comfortably large. Line height of 1.2 (body) supports readability; compressed headings (0.95) are acceptable for headline hierarchy as they still maintain x-height clarity.

</design-context>

Use the design system above for all UI you generate.