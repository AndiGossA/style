# Style Preferences

My standing preferences for how things should look and read. Anything built for
me should follow these unless I say otherwise on the day.

---

## The feeling

**Professional, considered, warm.** Editorial rather than corporate. Closer to
a well-set printed page than a SaaS dashboard.

- Light and warm by default — dusty pink grounds, never a dark tech theme
  unless I ask for one
- Generous whitespace; let things breathe rather than filling the screen
- Quiet structure: hairlines, small caps labels and alternating bands do the
  work, not boxes, shadows and colour blocks
- Restrained decoration — one considered mark beats five small flourishes

**Avoid:** gradient-heavy hero sections, emoji as iconography, drop shadows
used for depth, neon or saturated accents, stock-photo energy, anything that
reads as a template.

---

## Colour

The full palette with hex values, usage notes and contrast ratios lives in
[`tokens.css`](./tokens.css) and is documented in [`README.md`](./README.md).
The principles behind it:

- **Dusty pink is the ground**, not the accent — pages sit on `--paper`
  (`#F4E8E4`), with `--paper-deep` for alternating bands
- **Brown is structure and action** — headings, primary buttons, links
- **Pink is label and detail** — section labels, index numbers, accent rules
- **One accent per element.** Don't mix brown and pink in a single mark
- **Text is warm near-black brown** (`#2E211A`), never pure black or cool grey
- **Never hard-code a colour.** Every value comes from a token; override on
  `:root` if a project genuinely needs to differ

---

## Typography

- **Serif carries meaning, sans carries function.** Headings, figures, numbers
  and keys are serif; navigation, body copy, buttons and labels are sans
- **Source Serif 4** and **Inter** are the working pair — free stand-ins for
  Anthropic/Claude's licensed Styrene and Tiempos/Copernicus, which is the
  typographic feel I'm after
- Italic serif for the emphasised half of a headline, in `--brown-500`
- Small caps labels: uppercase, `0.1em` tracking, `--rose-600`
- Keep the measure: body copy at 62ch, ledes at 54ch, headlines around 15ch

---

## Layout

- Content capped at 1120px with a 28px gutter
- Sections alternate `--paper` and `.band`, closing on a `.band-dark` call to
  action
- Sticky top bar with a wordmark and anchor links on anything longer than a
  couple of screens
- Mobile is not an afterthought — check every layout at 390px before calling
  it done

---

## Motion

- Subtle and short: 0.15–0.18s, ease, on colour and small transforms only
- A 2px lift on hover is plenty
- Always honour `prefers-reduced-motion`

---

## Accessibility

Treated as a floor, not a finish.

- **WCAG AA minimum** on every text pairing — check before shipping, don't
  assume. If a colour I've asked for fails, tell me and propose the nearest
  passing value rather than shipping it quietly
- Visible `:focus-visible` outlines on everything interactive
- Real semantic HTML — `<section>`, `<article>`, headings in order
- Decorative SVG gets `aria-hidden="true"`

---

## Build

- **Plain HTML and CSS.** No framework, no build step, no dependencies unless
  the project genuinely needs one
- Static pages that work when opened from disk and on GitHub Pages
- Self-contained where practical; shared CSS where reuse matters more
- Comments explain *why*, not *what*

---

## Writing

For copy in anything built for me:

- Plain English, short sentences, no marketing inflation
- Specific over vague: "six quarters" not "a comprehensive timeframe"
- British spelling — prioritise, organise, colour
- Sentence case for headings, not Title Case
- Em dashes are fine; exclamation marks are not
- Don't explain the obvious back to me
