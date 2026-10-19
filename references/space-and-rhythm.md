# Space and Rhythm Reference

Original guidance on white space and rhythm as active design tools, distinct from the structural gutters/margins covered in grid-layout.md.

## Table of contents
- White space is not "leftover"
- Proximity: space as grouping
- Macro vs. micro white space
- Rhythm: spacing as cadence
- Common mistakes

## White space is not "leftover"

The instinct to fill empty areas on a page is usually wrong. White space (the term covers any empty area, not just literally white) does real work:

- It gives the eye a place to rest, which is what makes dense content feel approachable instead of overwhelming.
- It signals importance — generous space around a single element (a hero headline, a price) makes that element read as important *because* it's isolated. Crowding more content around it would dilute that signal.
- It's often the fastest fix for a page that "feels cluttered" even when no individual element is wrong — the problem is usually too little space between them, not anything about the elements themselves.

Treat white space as a layout decision with the same weight as choosing a font or a color, not as the default state before "real" content is added.

## Proximity: space as grouping

The core mechanic: **things that are spaced closer together read as related; things spaced farther apart read as unrelated**, regardless of whether they're visually similar otherwise. This is often a stronger signal to the eye than borders, background color, or dividers.

Practical application:
- A label and its input should sit closer to each other than to the next field's label — if the gap above a label equals the gap below it, the label visually floats between two fields instead of clearly belonging to one.
- Section spacing should be the largest gap on the page; paragraph spacing the smallest; everything in between (card gaps, group spacing) should step between those two extremes deliberately, not match one of them by accident.
- When a layout feels ambiguous about what goes with what, check proximity before adding a visual divider — often fixing the spacing removes the need for the divider entirely.

## Macro vs. micro white space

- **Macro white space** — the big gaps: page margins, space between major sections, the gutter around a hero image. This defines overall structure and pacing as someone scrolls.
- **Micro white space** — the small gaps: letter-spacing, line-height, padding inside a button or badge. This affects legibility and polish at close reading distance.

Both matter, but they fail differently: wrong macro spacing makes a page feel poorly structured at a glance; wrong micro spacing makes text/components feel cramped or sloppy on closer inspection. A page can get one right and still feel off because of the other — check both.

## Rhythm: spacing as cadence

Rhythm is what proximity and white space look like *repeated consistently down a page*. If every section uses the same vertical gap before it, and every paragraph the same gap, the reader's eye develops a predictable cadence — scrolling feels smooth rather than jumpy. See grid-layout.md's "combining type scale and grid" for the CSS mechanism (one base unit, everything else a multiple of it); this section is about the perceptual effect, that mechanism is the implementation.

Rhythm breaks down in two common ways:
- **Arbitrary variation** — section gaps of `48px`, `52px`, `40px` scattered across a page because each was tuned individually. The eye can't quite tell if it's intentional or sloppy, and it reads as the latter.
- **Monotony** — literally identical spacing everywhere, including around elements that are supposed to stand out. Rhythm needs *some* variation (bigger gaps around bigger things) to still convey hierarchy — perfectly uniform spacing flattens everything to the same importance.

## Common mistakes

- Reducing padding/margins to "fit more on the screen" when a page feels cramped — this is backwards; cramped pages usually need *more* space, achieved by cutting content or making the layout narrower, not by shrinking the space around what's already there.
- Adding a border or background color to separate two sections instead of simply increasing the space between them — space is often the lower-friction, more elegant fix.
- Using identical spacing for conceptually different gaps (the gap between a label and input vs. the gap between two unrelated form sections) — if those two gaps are visually equal, the layout has no proximity signal at all.
