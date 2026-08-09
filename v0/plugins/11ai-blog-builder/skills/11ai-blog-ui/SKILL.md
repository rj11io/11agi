---
name: 11agi-blog-ui
description: "Apply or recreate the 11agi-style polished editorial blog UI: dark/light tokenized theme, rounded hero card, collection browser controls, list/card result surfaces, publication headers, post reader layout, author cards, byline chips, responsive spacing, focus states, and accessible Tailwind/shadcn styling. Use after blog data/routes exist or when a user asks to make a blog visually match the 11agi editorial library."
---

# 11agi Blog UI

Implement the visual contract in [references/implementation.md](references/implementation.md). For a 11agi-style rebuild, also use [references/scaffold.md](references/scaffold.md). Use this after `$11agi-blog-cms`, `$11agi-blog-authors`, and `$11agi-blog-toc` have established the data and route behavior.

## Workflow

1. Inspect the host theme system, global CSS, Tailwind version, shadcn tokens, dark-mode mechanism, fonts, and existing component style conventions.
2. Preserve the host's token names where possible. Map the 11agi visual language onto `background`, `foreground`, `card`, `border`, `muted`, `primary`, `ring`, and chart/accent tokens rather than hard-coding colors.
3. Apply the editorial layout hierarchy: large rounded hero, compact uppercase labels, generous spacing, card/list surfaces, pill controls, and readable article width.
4. Style the library browser, publication pages, post readers, author pages, TOC, filters, empty states, and focus states as one cohesive system.
5. Verify keyboard focus, responsive breakpoints, dark mode, contrast, typecheck, lint, browser tests, and production build.

## Non-negotiable behavior

- Do not change content contracts or route behavior only for visual polish.
- Keep every interactive control keyboard reachable with visible focus.
- Keep one semantic link surface per result card/list item unless the host design intentionally uses separate controls.
- Use responsive grids with `minmax(0, 1fr)` or `min-width: 0` to avoid overflow.
- Preserve dark mode and reduced motion behavior.
- Do not introduce a UI library solely for this blog if Tailwind/shadcn conventions already exist.

## Delivery

Report token changes, component styling changes, responsive behavior, accessibility decisions, and visual deviations from the 11agi baseline.
