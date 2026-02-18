# Theme Foundation (Controlled Chaos)

This folder is the single source of truth for style alignment across the AIVC site.

## Files

- `tokens.css` — design tokens (color, type scale, spacing, radii, shadows, breakpoints)
- `typography.css` — font governance and lettering rules
- `motion.css` — interaction and reveal grammar
- `components.css` — base component primitives (panel, button, tag, container)
- `theme.css` — aggregator import file

## Import order

Use only:

```css
@import url('./styles/theme/theme.css');
```

This guarantees deterministic style layering.

## Controlled chaos rules

1. **Script font is strategic, not global**
   - Use script for hero words, company names, and high-emotion headers.
   - Do not use script in long paragraphs, tables, metadata, or nav menus.

2. **Sans is the readability backbone**
   - All dense information components (`EvaluatorCard`, transcript, scoreboard, memo body) should remain sans.

3. **Chaos is constrained to edge treatments**
   - Irregular radius variants (`panel--chaos-a/b/c`) can be mixed.
   - Keep spacing and typography strict to avoid visual drift.

4. **Accent discipline**
   - Maximum two accent colors per component.
   - Use status tones only for status meaning (INVEST/PASS/DIG DEEPER).

5. **Motion discipline**
   - Hover: quick and subtle.
   - Scroll reveal: soft fade-up.
   - Respect reduced-motion at all times.

## Recommended usage by module

- **Index Hero:** `.h-script-display` + `.script-pop`
- **Section headers:** `.h-display` or `.h-section` (sans)
- **Card titles:** `.h-card` (sans), optionally one script token inside title as accent
- **Metadata + labels:** `.text-meta`, `.text-label`
- **Prompt/code:** `.text-code` and `pre code`

## QA checklist for consistency

- [ ] Script font appears on purposeful headline moments only
- [ ] Body and cards stay sans for readability
- [ ] Panels use one of the chaos radius presets, not random custom radii
- [ ] Hover and reveal timings match motion tokens
- [ ] Focus states visible and accessible
