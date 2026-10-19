# Grid Systems Reference

Original guidance distilled from established column-grid design practice, translated for CSS Grid / Flexbox. A grid's job is to make unrelated elements on a page — a headline, a photo, a pull quote, a sidebar — feel like they belong to one system, by aligning them to a shared set of invisible lines.

## Table of contents
- Why grids matter on the web
- Choosing a column count
- Gutters and margins
- Translating a column grid to CSS Grid
- Baseline grids (vertical alignment)
- Combining type scale and grid into one spacing system
- Breaking the grid on purpose

## Why grids matter on the web

Without a grid, every component on a page tends to pick its own widths and alignments, and the page reads as a pile of boxes rather than a composition. A grid constrains *where things can start and stop* — not their content — so that a photo, a two-column text block, and a card list all share edges even though they're different kinds of content. The discipline is in the restraint: resisting a width or alignment that "would look fine alone" in favor of one the grid already offers.

## Choosing a column count

Pick a column count based on how much the layout needs to flex, not how it looks at one breakpoint:

- **4–6 columns** — simple pages, single content column with maybe a sidebar, blogs, docs.
- **8–12 columns** — pages with real layout variety: cards, multi-column feature sections, dashboards. 12 is the most common because it divides evenly by 2, 3, 4, and 6, so the same grid supports halves, thirds, and quarters without remainder.
- More columns than the page's actual layout needs just adds complexity — match the count to the widest variety of element widths you actually expect to need.

## Gutters and margins

- **Gutters** (space *between* columns) and **margins** (space *outside* the grid, at the page edge) should relate to the same spacing unit used elsewhere (see "Combining type scale and grid" below) rather than being picked independently.
- A common mistake: generous gutters but cramped outer margins (or vice versa) — the page edge usually wants margins **equal to or larger than** the gutter, not smaller, since the page edge is a stronger visual boundary than a gap between two related columns.
- On narrow viewports, margins often need to shrink proportionally more than gutters — preserve some breathing room at the edge even on mobile, but don't let it consume a disproportionate share of a small screen.

## Translating a column grid to CSS Grid

CSS Grid maps directly onto classic column-grid thinking:

```css
.page-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--gutter); /* same unit as the type/rhythm scale */
  max-width: var(--page-max-width);
  margin-inline: auto;
  padding-inline: var(--margin); /* outer margin */
}

/* A component spanning 8 of 12 columns, offset by 2 */
.feature {
  grid-column: 3 / span 8;
}
```

For responsive behavior, change the column math at breakpoints rather than the gutter/margin unit itself:

```css
@media (max-width: 640px) {
  .page-grid {
    grid-template-columns: repeat(4, 1fr); /* fewer columns, same gutter logic */
  }
}
```

`grid-template-columns: repeat(auto-fit, minmax(Xch, 1fr))` is useful for card grids that should reflow without explicit breakpoints, but it sacrifices precise column alignment with the rest of the page — use the explicit `repeat(12, 1fr)` approach when a component needs to align with text/headings elsewhere on the same page, and the flexible `auto-fit` approach for self-contained repeating components (card grids, galleries) where exact cross-component alignment matters less.

## Baseline grids (vertical alignment)

The column grid handles horizontal alignment; a baseline/vertical rhythm unit (see the web-typography reference) handles vertical alignment. The two should share a root unit where possible — e.g. if the body rhythm unit is `1.5rem`, consider making the grid gutter a multiple of that same `1.5rem`, so horizontal and vertical spacing feel related rather than coincidental.

This is harder to enforce exactly on the web than in print (text reflows, images have arbitrary aspect ratios), so treat it as a guiding preference, not a pixel-perfect requirement: when a choice of margin/padding is otherwise arbitrary, default to the rhythm unit or a simple multiple/fraction of it (×2, ×0.5) rather than inventing a new value.

## Combining type scale and grid into one spacing system

The strongest version of this approach uses a **single base unit** that drives three things at once: type scale, vertical rhythm, and grid gutters/margins. Example:

```css
:root {
  --unit: 1.5rem;         /* base rhythm unit, ~= body line-height */
  --gutter: var(--unit);
  --margin: calc(var(--unit) * 2);
  --space-xs: calc(var(--unit) * 0.5);
  --space-sm: var(--unit);
  --space-md: calc(var(--unit) * 2);
  --space-lg: calc(var(--unit) * 4);
}
```

Every subsequent spacing decision (padding inside a card, gap between sections, margin above a heading) pulls from this scale instead of a one-off value. This is the CSS equivalent of a modular scale applied to space instead of type size, and it's what makes a page look like it was designed as a system rather than assembled component-by-component.

## Breaking the grid on purpose

A grid is a tool for *consistency*, not a cage. Deliberately breaking it — a full-bleed image, a pull quote that overhangs the column — reads as a confident choice precisely because everything else on the page respects the grid. Breaking the grid only works as a technique if the break is rare and the rest of the page is disciplined; if everything breaks the grid a little, nothing reads as an intentional break.

## Proportion and pattern

A grid is also where two broader design principles become concrete on the web:

- **Proportion** — the relative size of elements to each other and to the page. A 12-column grid is itself a proportion system: a component spanning 4 columns is deliberately two-thirds the width of one spanning 6, not an arbitrary pixel value. When sizing a component, ask "what fraction of the grid is this" rather than "what width looks right" — the former composes with everything else on the page, the latter doesn't.
- **Pattern** — repetition with structure. A card grid, a table, a row of stat tiles all read as a pattern because every instance shares the same grid span, gutter, and internal spacing. Breaking that repetition (one card wider, one with different padding) reads as a bug unless it's signaling something meaningful (e.g. a featured item). Patterns are what let a reader scan a repeating section quickly instead of re-parsing each item from scratch.
