# Balance and Unity Reference

Original guidance on composition: does the page hold together as one thing, standing back from the individual parts covered in the other reference files.

## Table of contents
- Balance: symmetrical vs. asymmetrical
- Visual weight
- Movement: guiding the eye across the whole page
- Repetition as a unifying device
- Unity and harmony: the standing-back test

## Balance: symmetrical vs. asymmetrical

Balance means the page doesn't feel like it's about to tip over — visual weight is distributed so no one area overwhelms the rest.

- **Symmetrical balance** — mirrored or centered layouts. Reads as stable, formal, calm. Good fit for a lot of marketing/landing pages, forms, and anything where the tone should feel trustworthy and orderly.
- **Asymmetrical balance** — uneven layout (e.g. a large image on one side, a column of smaller text blocks on the other) that still balances because the *weights* are equalized, not the shapes. Reads as more dynamic and modern, and is usually necessary once a layout has to handle real, variable-length content (symmetry is easy with placeholder text, hard with a CMS feed).

Neither is "better" — the choice should match the tone the page needs. The common failure is accidental imbalance: a layout that was intended to be symmetrical but drifts off-center because of unequal content length, or an asymmetrical layout where one side is simply heavier with no compensating element on the other side.

## Visual weight

Weight isn't the same as physical size — it's perceived heaviness, and several things add to it independent of size: darker/more saturated color, more texture or detail, isolation (an element alone in a lot of white space can feel heavier than a cluster of small elements), and position (elements lower and to the right of a composition often carry slightly more visual weight in left-to-right reading cultures, a quirk from how the eye settles after scanning).

When a layout feels lopsided even though the boxes "measure" even, weight is usually the reason — a small, dark, isolated element can outweigh a larger, light, busy one.

## Movement: guiding the eye across the whole page

Movement is the path the eye takes through a composition, and it can be designed deliberately:

- Lines (literal dividers, or implied lines from alignment of edges) lead the eye in their direction.
- A sequence of decreasing size/contrast (hierarchy, see contrast-and-hierarchy.md) creates a path: eye lands on the biggest/boldest thing first, then follows to the next.
- Diagonal or curved arrangements (a staggered image grid, an S-curve of content blocks) feel more dynamic than a strict grid of equal rows, at some cost to scannability — use for exploratory/editorial content, not for a page meant to be scanned quickly for information.
- A dead end (a strong element near the edge of the page pointing further outward, e.g. a face looking off-frame, an arrow pointing off-screen) pulls the eye *off* the page — usually a mistake, and worth checking for in photography/illustration choices specifically.

## Repetition as a unifying device

Repetition (of color, shape, spacing, component style) is one of the cheapest ways to make a page feel like one system rather than a collection of separately-designed parts. This overlaps with "pattern" in grid-layout.md, but applies more broadly than just grid spans — a consistent corner-radius across every card/button/input, a consistent icon style, a consistent shadow depth, all repeat a small decision across many elements and the cumulative effect is a page that reads as designed by one hand.

The risk of repetition is monotony (see space-and-rhythm.md's note on this) — the fix is to repeat the *system* (spacing unit, corner radius, color roles) while still allowing content-driven variety (see contrast-and-hierarchy.md) within it.

## Unity and harmony: the standing-back test

Unity and harmony are the outcome, not a separate technique — they describe whether, after balance, weight, movement, and repetition are all working, the page reads as *one thing*. The practical check: close in on any individual component and it should look correct; step back and look at the whole page, and it should still look like it belongs to the same page. A common failure mode is a page built component-by-component where each piece is individually well-designed but pulled from different visual languages (different corner radii, different shadow styles, different spacing scales) — each part passes review alone, but the whole doesn't cohere. This is why the other five areas in this skill all point back to a small number of shared tokens (one spacing unit, one type scale, one color system, one grid) — unity is mostly a side effect of reusing the same small set of decisions everywhere, not a separate design pass at the end.
