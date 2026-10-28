# AI Design Tells Reference

Original guidance on a specific failure mode the other six reference files don't cover: patterns that aren't wrong by classic design principles, but are so overused by AI-generated UI specifically that they read as generic or unconsidered the moment a user recognizes them. Every LLM trained on a similar slice of the modern web, so left unguided, many independently converge on the same handful of defaults. Checking for these is a fast, separate pass — not a substitute for the six principle areas, but a sanity check once those are satisfied.

## Table of contents
- Why these are worth checking separately
- Typography tells
- Color tells
- Layout and component tells
- Motion tells
- Content/copy tells
- How to use this list

## Why these are worth checking separately

A page can nail measure, grid, contrast, and balance and still feel instantly recognizable as AI-generated, because the *specific values chosen* within those correct principles are the same ones almost every model reaches for by default. The six other reference files tell you a type scale needs a ratio — they don't tell you that defaulting to Inter at that scale is itself a tell. This file is a checklist of those specific, overused defaults, so a technically sound design doesn't still read as generic.

## Typography tells

- **Defaulting to Inter, or another single "safe" system/AI-default font, with no consideration of alternatives.** Not wrong on its own (Inter is a perfectly good typeface) — the tell is reaching for it automatically rather than as a deliberate choice among alternatives considered and rejected.
- **Letter-spacing added to body text "for polish."** Positive tracking on lowercase body copy almost always makes it slightly harder to read (see typography.md) — it's a common AI reflex because it looks neat in isolation, not because it helps the reader.
- **A huge, thin-weight hero headline with no supporting weight contrast elsewhere on the page** — striking in isolation, but if it's the only typographic flourish and everything else defaults to the same safe system stack, it reads as a template technique rather than a considered scale.

## Color tells

- **The purple-to-blue (or pink-to-orange) gradient**, especially on hero sections, buttons, or icon badges, used as instant "modern SaaS" styling rather than because it serves the brand or hierarchy.
- **Gray text set directly on a saturated colored background** (e.g. light gray text on a solid purple hero) — this usually fails contrast (see color.md) and is a common AI shortcut for "muted" text that doesn't account for the background changing.
- **Pure black (`#000`) or pure, untinted gray scales** rather than a neutral scale tinted slightly toward the brand hue — flat black/gray reads as an unconsidered default rather than a deliberate palette (see color.md's "building a palette from one role" section).
- **Using the same saturated accent color for everything** — links, primary buttons, icons, highlights, and borders all in one hue with no secondary or neutral tones to let it stand out (see color.md's 60/30/10 proportion guidance).

## Layout and component tells

- **Cards nested inside cards**, or a card used as the default wrapper for every piece of content regardless of whether grouping/elevation is actually needed. Reach for a card because it signals "grouped, interactive, elevated" — not as a default container for anything that needs a box around it.
- **A rounded-square icon tile centered above every section heading** — a specific, recognizable template pattern (icon in a soft-colored rounded square, centered, above a bolded title) repeated for every feature/benefit section on a page, regardless of whether an icon adds information there.
- **Identical card/section treatment repeated with no hierarchy between them** — three or more "feature" sections that are visually indistinguishable in importance, when the content underneath clearly has one primary message and supporting ones (see contrast-and-hierarchy.md).
- **Excessive border-radius on everything** (buttons, cards, inputs, badges all at the same very round radius) as a blanket "friendly/modern" default rather than a choice tied to the product's actual visual language.

## Motion tells

- **Bounce or elastic easing on standard UI transitions** (menus opening, modals appearing, buttons on hover) — it reads as a toy/demo feel rather than a considered interaction, and most interface motion is better served by a simple ease-out.
- **Every element on a page fading/sliding in on scroll**, applied uniformly regardless of whether that content benefits from an entrance animation — motion without a reason looks like a template effect, not a design decision.

## Content/copy tells

- **Generic placeholder-style microcopy that never got replaced with real specifics** — "Lorem ipsum"-adjacent filler like "Amazing feature description goes here" left in a shipped-looking design, or headlines so generic they could apply to any product ("Powerful. Simple. Fast.").
- **Overuse of em dashes and exclamation points in marketing copy**, or a uniformly upbeat, adjective-heavy tone across every section regardless of what's being described — a stylistic tell independent of whether the copy is accurate.

## How to use this list

Run this as a final, fast pass after the six principle areas check out — it's a different kind of check (pattern recognition, not calculation) and works best as a last look at the whole page rather than a line-by-line review. If a design trips several of these, it's worth asking whether each choice was made deliberately for this product, or just inherited because it's the default move. None of these are permanently banned — a gradient or a bounce animation can be the right call for a specific brand — the tell is using them unconsidered, as the default rather than a choice.
