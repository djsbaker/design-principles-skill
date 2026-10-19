# Color Reference

Original guidance on using color as a functional design tool rather than decoration.

## Table of contents
- Color's two jobs: hierarchy and identity
- Building a palette from one role, not one hue
- Proportion: the 60/30/10 habit
- Contrast and accessibility
- Color isn't the first line of hierarchy

## Color's two jobs: hierarchy and identity

Color does two distinct things on a page, and conflating them causes most color mistakes:

- **Hierarchy** — color tells the reader what matters (a primary action button, an error state, a visited link). This use should be sparse and consistent: one color always means "primary action," never sometimes decoration and sometimes meaning.
- **Identity** — color carries brand/mood (a hero background, an illustration palette). This use can be freer, but shouldn't compete with the hierarchy colors on the same screen.

Before adding a color to a design, ask which job it's doing. A palette that mixes the two without distinguishing them (brand purple used for both the logo *and* for "destructive action" buttons) will confuse users.

## Building a palette from one role, not one hue

Don't start a palette by picking pretty hues. Start by listing the *roles* color needs to fill, then assign:

- **Neutral scale** (grays, usually 5–9 steps from near-white to near-black) — backgrounds, borders, body text. This does most of the work on a typical page.
- **Primary** — one brand hue for primary actions/emphasis.
- **Semantic set** — success, warning, danger, info — conventionally green/yellow-orange/red/blue, because reversing these conventions fights user expectation for no benefit.
- **Secondary/accent** (optional) — a second hue for data visualization or a complementary action tier.

Each role should have a **range of steps** (light→dark), not one fixed value, so the same role can be used for a background (very light step), text on that background (dark step, meeting contrast), and a border (mid step) — all clearly related, not independently chosen.

```css
:root {
  --gray-50: #f9fafb;
  --gray-500: #6b7280;
  --gray-900: #111827;
  --primary-500: #2563eb;
  --primary-700: #1d4ed8; /* for text/icons on a light background, meeting contrast */
  --danger-500: #dc2626;
}
```

## Proportion: the 60/30/10 habit

A simple, reliable starting ratio for how much of a screen each role occupies:

- **~60%** neutral/background — the page should be mostly quiet.
- **~30%** secondary — surfaces, cards, secondary text, borders.
- **~10%** accent/primary — the color that's supposed to grab attention (primary buttons, active states, key data points).

This isn't a rule to measure pixels against, but a sanity check: if a page feels "loud" or "busy," it's usually because the accent color's share has crept well past 10% — every button, link, and icon is the brand color, so nothing stands out as *the* thing to notice.

## Contrast and accessibility

- Body text against its background should meet **WCAG AA**: contrast ratio ≥ 4.5:1 for normal text, ≥ 3:1 for large text (≥24px, or ≥19px bold). This isn't just a compliance checkbox — insufficient contrast makes text measurably harder to read for everyone, not only users with low vision.
- Don't rely on color alone to convey meaning (a red border alone for "error," green alone for "success") — pair it with an icon, label, or pattern so the information survives for colorblind users and in grayscale printouts.
- Check contrast at the actual text color/weight/size used, not the swatch in isolation — a color that passes at 16px bold may fail at 13px regular.
- Tools: any WCAG contrast checker; don't eyeball this one, since human color perception is a poor judge of exact ratios.

## Color isn't the first line of hierarchy

A common mistake is reaching for color to establish hierarchy before size, weight, and spacing have done their job (see contrast-and-hierarchy.md). Color is best used to **reinforce** a hierarchy that already exists structurally — a bigger, bolder heading that's also colored differently reads clearly; a same-size, same-weight heading that relies on color alone to stand out is fragile (fails in grayscale, fails for colorblind users, fails if the color is ever muted for a dark-mode variant).
