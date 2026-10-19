# Web Typography Reference

Original guidance distilled from established web-typography practice. Numbers are starting points, not laws — adjust for typeface, audience (e.g. long-form reading vs. dense UI), and context.

## Table of contents
- Measure (line length)
- Leading (line-height)
- Vertical rhythm
- Modular type scales
- Font pairing
- Hanging punctuation and micro-typography
- Responsive type

## Measure (line length)

The measure is how many characters fit on one line. Too long, and the reader's eye has trouble finding the start of the next line on the return sweep — they lose their place or re-read lines. Too short, and reading becomes stop-start, breaking the eye's rhythm and forcing too many line breaks per thought.

- Target **45–75 characters per line** for continuous body text; **~66 characters** is the commonly cited sweet spot.
- Implement with `max-width` in `ch` units (1`ch` ≈ the width of "0" in the current font), e.g. `max-width: 66ch`, applied to the text container — not the whole viewport.
- Narrower measures (35–45ch) work for sidebars, captions, or pull quotes, where short bursts of text are expected.
- Multi-column layouts should narrow each column's measure rather than letting a single column run wide, if columns are used for body text at all.

## Leading (line-height)

Leading is the vertical space between baselines. It needs to scale with measure and type size:

- **Body text, moderate measure (50–70ch): `line-height: 1.4–1.6`.**
- Wider measures need *more* leading — extra vertical space gives the eye a visual cue to find the next line, compensating for the longer horizontal sweep.
- Narrower measures (captions, UI labels, pull quotes) can run tighter, sometimes down to 1.2–1.3.
- Smaller or lighter-weight text generally wants slightly more leading than larger or bolder text at the same measure — small/light text is harder to track line-to-line.
- Headings typically want *tighter* leading than body text (1.1–1.3), since each line is shorter and the type is larger — big gaps between heading lines read as disconnected.

## Vertical rhythm

Rhythm is what makes a page feel considered rather than assembled. The core idea: define one base vertical unit (usually the body line-height) and make every significant vertical measurement — paragraph spacing, margins above/below headings, space around images — a multiple of that unit.

Practical approach:
1. Pick a base line-height, e.g. `1.5rem`.
2. Express spacing as multiples: paragraph gap = `1 × 1.5rem`, section gap = `2 × 1.5rem`, etc.
3. In CSS, store the unit as a custom property (`--rhythm: 1.5rem`) and derive everything else (`margin-bottom: calc(var(--rhythm) * 2)`), rather than hand-picking pixel values per element.
4. Headings break the grid in *font-size* but should still land back on the rhythm in total block height where practical (this is harder to get exact on the web than in print, and is a "nice to have," not a hard requirement).

This single habit — one base unit, everything else derived — is the highest-leverage typographic practice for web work, because it prevents the slow accumulation of slightly-different spacing values that makes a page feel inconsistent.

## Modular type scales

A type scale is a set of sizes related by a constant ratio, so that each heading level is a predictable step up or down from the next, rather than arbitrarily chosen.

Common ratios and when to use them:
- **1.125 (major second)** — subtle, good for dense UI/dashboards with many heading levels.
- **1.2 (minor third)** — safe general-purpose default.
- **1.25 (major third)** / **1.333 (perfect fourth)** — more dramatic, good for editorial/marketing pages where headline impact matters.
- **1.5–1.618 (perfect fifth / golden ratio)** — large jumps, best for pages with only one or two heading levels that need to pop.

To build one: pick a base size (body text, e.g. `1rem` = 16px) and a ratio `r`. Each step up multiplies by `r`; each step down divides by `r`. In CSS:

```css
:root {
  --scale-ratio: 1.25;
  --text-base: 1rem;
  --text-sm: calc(var(--text-base) / var(--scale-ratio));
  --text-lg: calc(var(--text-base) * var(--scale-ratio));
  --text-xl: calc(var(--text-lg) * var(--scale-ratio));
  --text-2xl: calc(var(--text-xl) * var(--scale-ratio));
}
```

Don't hand-tune individual heading sizes after this — if `h2` "feels too big," change the ratio or base, not that one value, or the scale stops being a scale.

## Font pairing

Pairing two typefaces works best when they contrast in *purpose*, not just in superficial style:

- Pair a **text face** (designed for extended reading — moderate contrast, open counters, reliable at small sizes) with a **display face** (designed to be read in short bursts — can have more personality, higher contrast, tighter spacing) used only for headings/accents.
- Avoid pairing two faces that are similar-but-not-identical (e.g. two different geometric sans faces) — the near-match reads as a mistake rather than an intentional choice. Either match exactly (use one family's weights) or contrast clearly (serif + sans, or geometric + humanist).
- Limit a typical page to **two font families** total (optionally a third monospace face for code). More than that fragments the page's visual identity.
- Variable fonts and well-stocked font families (multiple weights, true italics) often make a second family unnecessary — a single family used well (regular, medium, bold, italic) can carry an entire page.

## Hanging punctuation and micro-typography

Small details that matter disproportionately for polish:

- **Hanging punctuation**: quotation marks, bullets, and some punctuation can hang slightly outside the text block's edge so the *letters* align optically rather than the marks themselves. CSS: `hanging-punctuation: first last` (support varies; treat as progressive enhancement).
- **Real quotation marks and apostrophes** (`“ ” ‘ ’`) instead of straight quotes (`" '`) — use proper Unicode characters or CSS `quotes`/typographic-replacement tooling, not literal straight quotes in body copy.
- **Non-breaking spaces** before units, between initials, and in other places a line break would look wrong (`10 MB`, `J. R. R. Tolkien`) — use `&nbsp;` or ` `.
- **Widows and orphans**: avoid a heading or paragraph's last line consisting of a single short word stranded alone. CSS `text-wrap: pretty` (and `text-wrap: balance` for headings) now handles much of this automatically in modern browsers — prefer it over manual `<br>` insertion.
- **Letter-spacing**: slightly increase tracking for all-caps text (caps set at normal tracking look cramped); never add positive tracking to lowercase body text, which hurts readability.

## Responsive type

- Prefer **relative units** (`rem` for font-size, `ch`/`%` for measure) over fixed `px`, so text respects user zoom/base-font preferences.
- Use `clamp()` for fluid type that scales between a minimum and maximum across viewport widths, e.g. `font-size: clamp(1rem, 0.9rem + 0.5vw, 1.25rem)`, instead of discrete breakpoint jumps — this keeps the scale's ratios intact across screen sizes rather than recalculating them per breakpoint.
- Re-check measure at each breakpoint — a layout that's 66ch on desktop may need a different `max-width` (or none at all, relying on padding) on narrow viewports where the container is already narrower than the ideal measure.
- Line-height set in unitless numbers (e.g. `1.5`, not `24px`) scales correctly with the element's own font-size, which matters once font-size itself is fluid.
