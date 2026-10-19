# Example: site header / nav bar

A product header with logo, nav links, and auth actions, styled two ways: [`before.html`](before.html) without the skill, [`after.html`](after.html) with it applied. Same markup, same links — only the CSS changes.

## Before

![Before: cramped nav, one link randomly bigger and bolder, weak spacing between groups](before.png)

## After

![After: evenly spaced nav, consistent link weight, clear grouped actions](after.png)

## What changed, and why

| Issue in `before.html` | Fix in `after.html` | Principle / reference |
|---|---|---|
| "Pricing" is randomly larger and bolder than the other three nav links for no functional reason (not the active page, nothing marks it as current) | All nav links share the same size/weight — variety that doesn't map to meaning reads as a mistake | Contrast & hierarchy — [`references/contrast-and-hierarchy.md`](../../references/contrast-and-hierarchy.md) |
| Spacing between the logo, nav links, and actions is inconsistent (`20px`, `10px`, `8px`) with no shared unit, so the header's internal grouping is ambiguous | All gaps derive from one `--space: 1rem` unit, with a larger gap between the three logical groups (logo / nav / actions) than within each group | Space & rhythm — [`references/space-and-rhythm.md`](../../references/space-and-rhythm.md) |
| "Sign in" and "Get started" aren't visually grouped — they just happen to sit next to each other at the end of a flex row | Wrapped in an `.actions` container with its own consistent gap, so proximity signals they're one unit (secondary + primary action) | Space & rhythm — [`references/space-and-rhythm.md`](../../references/space-and-rhythm.md) |
| Logo is plain text at a smaller size than some nav links — it doesn't read as the anchor of the header | Logo gets a mark (SVG) + bold weight, clearly the most stable, recognizable element in the row | Balance & unity — [`references/balance-and-unity.md`](../../references/balance-and-unity.md) |

## Reproducing this

```bash
cd examples/site-header
python3 -m http.server 8000
# then open http://localhost:8000/before.html and /after.html
```
