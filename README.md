# style

My design system and standing style preferences, kept in one place so every
project starts from the same look.

| File | What it is |
|---|---|
| [`PREFERENCES.md`](./PREFERENCES.md) | The preferences themselves — feel, colour, typography, layout, motion, accessibility, writing. Read this first. |
| [`tokens.css`](./tokens.css) | Every colour, type, space, radius and shadow value as CSS custom properties. The single source of truth. |
| [`base.css`](./base.css) | Element defaults and components — buttons, cards, stat rows, timeline rail, definition rows, sticky bar, hero, light and dark bands. Requires `tokens.css`. |
| [`index.html`](./index.html) | The living style guide: swatches, type scale, every component rendered, house rules. |

**Live guide:** open `index.html`, or enable GitHub Pages on this repo to
publish it.

## Use it in a project

Copy `tokens.css` and `base.css` into the project, then in your `<head>`:

```html
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Source+Serif+4:opsz,wght@8..60,400;8..60,600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="tokens.css">
<link rel="stylesheet" href="base.css">
```

While this repo is public you can link the files directly instead of copying:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/AndiGossA/style@main/tokens.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/AndiGossA/style@main/base.css">
```

Then write plain markup:

```html
<section class="band">
  <div class="wrap">
    <div class="section-head">
      <span class="tag">Section label</span>
      <h2>Section heading</h2>
      <p>A sentence of supporting copy.</p>
    </div>
    <div class="card-grid">
      <article class="card card-ruled">
        <span class="num">01</span>
        <h3>Card title</h3>
        <p>Card body copy.</p>
      </article>
    </div>
  </div>
</section>
```

## Use it with Claude Code

Add this to another project's `CLAUDE.md` so sessions there pick the
preferences up automatically:

```markdown
## Style
Follow my standing style preferences: https://github.com/AndiGossA/style
Palette, typography and component conventions are in that repo's
PREFERENCES.md, tokens.css and base.css. Don't invent a new palette.
```

## Palette

### Grounds

| Token | Hex | Use |
|---|---|---|
| `--surface` | `#FFFAF8` | Cards, raised panels |
| `--paper` | `#F4E8E4` | Page background |
| `--paper-deep` | `#ECDAD5` | Alternating section bands |
| `--line-soft` | `#EBD8D2` | Hairlines inside components |
| `--line` | `#E0C9C2` | Borders, dividers |

### Brown

| Token | Hex | Use |
|---|---|---|
| `--brown-900` | `#2E211A` | Body text, inverted bands |
| `--brown-700` | `#5A3D2E` | Primary buttons, links |
| `--brown-500` | `#8A5A42` | Emphasis, accent rules |
| `--brown-300` | `#B98C71` | Decorative only |

### Dusty pink

| Token | Hex | Use |
|---|---|---|
| `--rose-600` | `#8A524F` | Labels, small caps — **the only pink cleared for text** |
| `--rose-500` | `#A9706C` | Decorative marks, accent rules |
| `--rose-400` | `#C99A95` | Decorative, buttons on dark bands |
| `--rose-200` | `#E8D2CD` | Hover borders |
| `--rose-050` | `#F6EBE8` | Tint washes, hover fills |

## Typography

Anthropic/Claude use Styrene (sans) and Tiempos/Copernicus (serif), both
licensed. This system uses the closest freely available stand-ins:

- **Source Serif 4** — headings, figures, keys
- **Inter** — navigation, body copy, buttons, labels

Holding licences for the real faces? Swap the `--serif` and `--sans` values in
`tokens.css`; nothing else needs to change.

## Accessibility

Contrast ratios measured against `--paper` (`#F4E8E4`):

| Pairing | Ratio | WCAG |
|---|---|---|
| `--ink` body text | 13.0:1 | AAA |
| `--ink-muted` secondary text | 5.4:1 | AA |
| `--rose-600` labels | 5.2:1 | AA |
| `--brown-700` links | 8.2:1 | AAA |
| `--ink-invert` on `--brown-700` (primary button) | 9.4:1 | AAA |
| `--brown-900` on `--rose-400` (dark-band button) | 6.3:1 | AA |

On `--paper-deep`, `--rose-600` measures 4.6:1 and `--ink-muted` 4.8:1 — both
still AA. Re-check any pairing you introduce.

Components ship with `:focus-visible` outlines and honour
`prefers-reduced-motion`.

## Browser support

Modern evergreen browsers. `color-mix()` is used once, for the sticky bar's
translucent background, with a solid fallback declared immediately before it.

## Used by

- [Lifestyle Plan](https://github.com/AndiGossA/test) — landing page built on
  these tokens
