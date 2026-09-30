---
name: section-layouts
description: Catalog of wireframe layouts for marketing sections (hero, pricing, FAQ, footer, testimonials, team, blog and more) and auth screens (login, register). Use when building a landing page or app screen and choosing how a section should be laid out, or when asked for layout variations of a section.
---

# Section Layouts

Wireframes (SVG) live in `${CLAUDE_PLUGIN_ROOT}/skills/section-layouts/prompts/<group>/<section>/<n>-<layout-name>.svg`. The file name describes the layout. Open the SVG to see the structure: block positions, proportions, alignment.

Wireframes define **structure only**. Colors, type, spacing and radius come from the design system in use (see `design-references`) and the principles in `ui-fundamentals`.

## Catalog

### Marketing

| Section | Layout |
|---|---|
| blog | `2-trending-topics-categorized-link-columns` |
| contact | `1-centered-heading-supporting-copy-and-stacked-form-with-dual-actions` |
| content | `1-two-column-split-copy-and-ctas-left-video-placeholder-right` |
| cta | `2-centered-headline-paragraph-and-dual-rounded-buttons` |
| customer-logo | `1-centered-kicker-and-single-wrapping-logo-row` |
| event-schedule | `2-centered-single-day-ruled-timeline` |
| faq | `1-centered-heading-with-single-column-accordion` |
| feature | `1-left-aligned-intro-with-six-up-icon-grid` |
| footer | `1-logo-links-and-copyright-centered-stack` |
| hero | `1-centered-stack-with-big-image-below` |
| newsletter | `1-centered-stack-with-floating-avatar-portraits` |
| portfolio | `2-uniform-six-card-grid` |
| pricing | `1-three-pricing-cards-in-a-row` |
| social-proof | `1-centered-inline-stat-row` |
| team | `1-four-column-grid-with-badge-role-and-contact-action` |
| testimonials | `1-centered-single-testimonial-with-decorative-quote-mark` |

### Application

| Screen | Layout |
|---|---|
| login | `2-default-centered-card` |
| register | `1-default-centered-card` |

The numeric prefix is the layout's id in the original set; gaps (e.g. only `2-` for blog) mean other variants are not included here.

## How to use

1. Identify the section being built and open its wireframe.
2. Reproduce the structure (columns, alignment, hierarchy, number of items), then style it with the active design system's tokens.
3. Adapt the content count and copy to the product; keep the layout's logic, not its placeholder.
4. On a full page, **vary** layouts across sections (don't stack several centered stacks in a row). Alternate alignment and density to keep rhythm.
5. When the user asks for variations and only one wireframe exists, derive alternatives yourself (e.g. left-aligned vs centered, split vs stacked) and say they are your own variants.

## Scope

Marketing layouts target marketing and e-commerce surfaces. Dashboards and app shells follow the design system's app layout, not these sections.

Wireframes adapted from [typeui](https://github.com/bergside/typeui) (MIT, © Bergside LLC).
