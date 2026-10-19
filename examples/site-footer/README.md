# Example: site footer

A three-column footer with legal line, styled two ways: [`before.html`](before.html) without the skill, [`after.html`](after.html) with it applied. Same markup, same links — only the CSS changes.

## Before

![Before: cramped columns with no grouping, flat low-contrast headings](before.png)

## After

![After: clear column headings, consistent spacing, legible copyright line above a divider](after.png)

## What changed, and why

| Issue in `before.html` | Fix in `after.html` | Principle / reference |
|---|---|---|
| Column headings ("Product," "Company," "Resources") are the same size, weight, and color as the links beneath them — no visual distinction between a group label and its items | Headings are bold, uppercase, slightly tracked, and a lighter color than the links — clearly a label, not a link | Contrast & hierarchy — [`references/contrast-and-hierarchy.md`](../../references/contrast-and-hierarchy.md) |
| Column gaps (`14px`) and link spacing (`2px`) are both arbitrary and nearly the same value, so columns and their contents don't read as distinct groups | Column gap is a full `--space` unit, link padding is a fraction of it — the size difference between the two makes the grouping legible | Space & rhythm — [`references/space-and-rhythm.md`](../../references/space-and-rhythm.md) |
| Columns use `flex` with manual `margin-right` on each — adding or removing a column means recalculating spacing by hand | `grid-template-columns: repeat(3, minmax(0, 1fr))` — columns are always even widths, any count just works | Grid & layout — [`references/grid-layout.md`](../../references/grid-layout.md) |
| The copyright line floats directly under the links with no separation, and its color is barely distinguishable from the background | A `border-top` divider plus consistent spacing separates it as its own zone, and its color is dialed up just enough to stay legible without competing with the nav links above | Color — [`references/color.md`](../../references/color.md) |

## Reproducing this

```bash
cd examples/site-footer
python3 -m http.server 8000
# then open http://localhost:8000/before.html and /after.html
```
