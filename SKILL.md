---
name: design-principles
description: Apply core visual-design principles — typography, grid/layout, color, white space, contrast/hierarchy, and balance/unity — when writing or reviewing HTML/CSS, critiquing a UI or mockup, or generating a design system/spec. Use this whenever the user is building a web page, app UI, marketing page, dashboard, or design system and cares about readability, polish, or "why does this look off," even if they don't name a specific principle — triggers include requests to style a page, fix a layout that feels "cramped," "unbalanced," "busy," or "flat," set up a type/color/spacing scale, build a grid, choose fonts or colors, or review a design/screenshot for visual issues.
---

# Design Principles

Good design is mostly invisible: nobody notices it, they just find the thing easy to read, easy to scan, and easy to trust. This skill applies six core principles of visual design — refined across print and screen design for decades — to web and UI work. Every rule here exists because it measurably helps or hurts how a page is perceived, not because it's decorative convention.

Use this skill when:
- Writing or reviewing CSS/markup for any visual page (articles, docs, marketing, dashboards, apps)
- A design looks "off" but it's hard to say why
- Setting up a type scale, color palette, spacing scale, or grid from scratch
- Reviewing a design, mockup, or screenshot for visual issues

## The six areas

Each area has a dedicated reference file with the full reasoning, numbers, and CSS patterns. Read the relevant file(s) before making a recommendation — don't rely on the one-line summary below alone.

| Area | Covers | Reference |
|---|---|---|
| **Typography** | Measure, leading, vertical rhythm, type scale, font pairing, micro-typography | [references/typography.md](references/typography.md) |
| **Grid & layout** | Column grids, gutters/margins, proportion, pattern/repetition in layout | [references/grid-layout.md](references/grid-layout.md) |
| **Color** | Palette structure, contrast/accessibility, color as hierarchy vs. decoration | [references/color.md](references/color.md) |
| **Space & rhythm** | White space as an active element, proximity/grouping, spacing cadence | [references/space-and-rhythm.md](references/space-and-rhythm.md) |
| **Contrast & hierarchy** | Emphasis, visual hierarchy, variety — what draws the eye and in what order | [references/contrast-and-hierarchy.md](references/contrast-and-hierarchy.md) |
| **Balance & unity** | Balance, movement, repetition, unity/harmony — does the composition hold together | [references/balance-and-unity.md](references/balance-and-unity.md) |

## Diagnostic order

When something "looks off," these six areas aren't independent — some are foundational and others are refinements on top. Check in roughly this order:

1. **Grid & layout** — is there a structural system at all, or is every element sized/positioned independently?
2. **Typography** — within that structure, is text set at a readable measure/leading/scale?
3. **Space & rhythm** — is spacing consistent and used to group related things / separate unrelated things?
4. **Contrast & hierarchy** — once the structure and type are sound, does the eye know where to go first, second, third?
5. **Color** — is color reinforcing that hierarchy, or competing with it / failing accessibility contrast?
6. **Balance & unity** — standing back from the whole page, does it feel like one composition, or a pile of separately-styled parts?

Most "unprofessional" or "cluttered" complaints trace back to #1–#3. Most "flat" or "hard to scan" complaints trace back to #4–#5. #6 is usually the last 10%: everything individually fine, but the whole not reading as a unit.

## Applying this in practice

- **Writing new CSS**: establish the grid and a single spacing/type unit first (see grid-layout.md's "combining type scale and grid"), then layer color and hierarchy decisions on top of that structure — don't pick colors or type sizes before the structural scale exists.
- **Reviewing existing CSS or a screenshot**: walk the diagnostic order above and name the specific property/value or design choice that's off, with a concrete fix — not vague aesthetic feedback like "make it pop."
- **Generating a spec** (type scale, color palette, spacing scale, grid): derive values from one base and one ratio/relationship each, and hand back actual CSS custom properties or tokens, not hand-picked one-off values.
- Always explain *why* a choice works, not just that it's a rule — the goal is for the user to make the next call themselves.
