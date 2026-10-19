# design-principles

A [Claude](https://claude.com) skill that applies core visual-design principles — typography, grid/layout, color, white space, contrast/hierarchy, and balance/unity — when writing or reviewing HTML/CSS, critiquing a UI, or generating a design system spec.

## What it covers

Thirteen classic design principles, organized into six reference files so each stays focused and none duplicates another:

| Area | Principles covered | File |
|---|---|---|
| Typography | Measure, leading, vertical rhythm, type scale, font pairing, micro-typography | [`references/typography.md`](references/typography.md) |
| Grid & layout | Column grids, gutters/margins, proportion, pattern | [`references/grid-layout.md`](references/grid-layout.md) |
| Color | Palette roles, 60/30/10 proportion, accessible contrast | [`references/color.md`](references/color.md) |
| Space & rhythm | White space, rhythm | [`references/space-and-rhythm.md`](references/space-and-rhythm.md) |
| Contrast & hierarchy | Contrast, emphasis, hierarchy, variety | [`references/contrast-and-hierarchy.md`](references/contrast-and-hierarchy.md) |
| Balance & unity | Balance, movement, repetition, unity, harmony | [`references/balance-and-unity.md`](references/balance-and-unity.md) |

`SKILL.md` is the entry point: it gives Claude a diagnostic order to work through these six areas and points into the relevant reference file(s) for the full reasoning, numbers, and CSS patterns.

## Installing

**Claude Code**: copy (or symlink) this repo into your skills directory, e.g. `~/.claude/skills/design-principles/`, keeping the folder name and the `SKILL.md` + `references/` layout intact.

**claude.ai / Claude Desktop with skill support**: package it as a `.skill` file (a zip of this repo's contents) and use "Save skill" to install it to your profile. If you have the [skill-creator](https://github.com/anthropics/skills) tooling, run:

```bash
python -m scripts.package_skill /path/to/design-principles-skill
```

## Examples

See the applied skill's effect side by side in [`examples/dashboard-card`](examples/dashboard-card): the same markup styled without the skill (`before.html`) and with it (`after.html`), plus a fix-by-fix table linking each change back to a principle and reference file.

## Why these six files

The 13 terms (emphasis, balance, contrast, repetition, proportion, movement, white space, rhythm, pattern, hierarchy, variety, unity, harmony) are a standard "elements and principles of design" taxonomy taught broadly in design education. Several overlap heavily in practice — unity, harmony, and balance all describe whether a composition coheres; repetition, pattern, and rhythm all describe structured recurrence — so they're grouped by what they actually diagnose rather than split into 13 thin files.

## Relationship to other skills

This skill deliberately stays in its lane: composition fundamentals (typography, grid, color, space, hierarchy, balance) once a design direction already exists. It doesn't overlap with:

- **Motion/animation skills** (e.g. `emilkowalski/skills`, `design-motion-principles`) — those cover transitions, easing, and animated interaction; this skill is static-composition only.
- **`ui-ux-pro-max-skill`**-style catalog skills — those pick an industry-appropriate palette and pattern from a pre-built library at the start of a project; this skill reasons about whether a given composition (whatever palette/pattern was chosen) actually works, and how to fix it if not.

The two kinds of skill are complementary and can run together: a catalog skill picks the direction, this one critiques and refines the execution. See the Precedence section in [`SKILL.md`](SKILL.md) for how conflicts between this skill and a project's own brand/theme system (or another installed design skill) should be resolved.

## A note on sources

This skill is original writing. It's informed by widely-taught, general design knowledge — the kind of thing foundational texts like Robert Bringhurst's *The Elements of Typographic Style* and Josef Müller-Brockmann's *Grid Systems in Graphic Design* are known for articulating — but it does not quote, closely paraphrase, or reproduce content from those or any other specific book. If you want the skill to reflect a particular source's exact framework or terminology more closely, open an issue or PR with the relevant excerpt and a proposed edit.

## Contributing

PRs welcome — especially real-world CSS examples, corrections to the numeric guidance, or additional reference files for principles not yet covered (e.g. motion/animation, iconography).

## License

MIT — see [LICENSE](LICENSE).
