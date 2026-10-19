# Contrast and Hierarchy Reference

Original guidance on directing attention: contrast, emphasis, hierarchy, and variety as one connected toolset.

## Table of contents
- Hierarchy is a reading order, not a style
- Contrast is what makes hierarchy visible
- The four contrast levers
- Variety without chaos
- Checking hierarchy without the content

## Hierarchy is a reading order, not a style

Visual hierarchy means: if you glance at the page for half a second, what do you see first, second, third? That order should match the actual importance of the content. A page can be beautifully styled and still have broken hierarchy if, say, a secondary caption is visually louder than the headline it supports.

Before styling anything, write down the intended reading order in plain language (e.g. "price, then product name, then description, then fine print"). Then check whether the current styling produces that order. If it doesn't, no amount of polish on individual elements fixes it — the relationships between elements need to change.

## Contrast is what makes hierarchy visible

Hierarchy is the *intent* (what should stand out); contrast is the *mechanism* (what actually makes something stand out). Without sufficient contrast between levels, a hierarchy exists on paper but not to the eye — two heading levels that differ by 2px in size and one font-weight step will not read as meaningfully different, no matter how logically they're nested in the markup.

The test: squint at the page, or shrink it to thumbnail size. If you can still tell what the most important element is, the contrast is working. If everything blurs into the same gray mass, contrast is too subtle somewhere.

## The four contrast levers

Contrast isn't just about color. Four independent levers can each create it, and combining them is usually stronger than maxing out one:

1. **Size** — bigger reads as more important. The most immediate lever, and the one a type scale (see typography.md) formalizes.
2. **Weight** — bold vs. regular, or a heavier vs. lighter font in a variable family. Works even when size can't change (e.g. inline text).
3. **Color/value** — darker/more saturated vs. lighter/muted (see color.md for using this deliberately rather than decoratively).
4. **Space** — more space *around* an element isolates it and raises its perceived importance (see space-and-rhythm.md).

A strong hierarchy usually layers two or more of these for the top level (e.g. a hero headline that's both large *and* has more space around it) and relies on just one subtle lever for minor distinctions (e.g. a timestamp that's only slightly muted in color, nothing else different) — not every contrast needs every lever at once.

## Variety without chaos

Variety means not every element at the same hierarchy level looks identical — it keeps a long page (a list of articles, a feed, a dashboard) from feeling monotonous. But variety needs a boundary, or it undermines hierarchy instead of supporting it:

- Vary within a level, not across levels — different article thumbnails and excerpt lengths in a feed is variety; different heading *styles* for what should be equivalent headings is inconsistency.
- Variety should come from the content (an image some cards have and others don't, different data visualizations), not from arbitrarily restyling the same kind of element differently each time it appears.
- If removing the variety would make two things that are *supposed* to be different look the same, the variety is doing real work. If removing it would make no functional difference, it's probably just noise.

## Checking hierarchy without the content

A fast diagnostic: replace all text with gray boxes/lorem ipsum of the correct size and weight, remove color, and look at the layout in grayscale. If the intended reading order is still obvious from size/weight/space alone, the hierarchy is built on solid contrast fundamentals rather than leaning on color or copy to do the work that layout should be doing.
