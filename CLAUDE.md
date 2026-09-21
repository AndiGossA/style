# style

This repo holds my design system and standing style preferences.

- `PREFERENCES.md` is the source of truth for taste decisions — feel, colour,
  typography, layout, motion, accessibility and writing. Read it before
  changing anything here, and follow it in any project that references this
  repo.
- `tokens.css` holds every colour, type, space and elevation value. Never
  hard-code a colour anywhere; add or adjust a token instead.
- `base.css` holds element defaults and components, and depends on
  `tokens.css` being loaded first.
- `index.html` is the living style guide. Any token or component added here
  must also be rendered and documented on that page, or it doesn't exist.

When a token changes, check the contrast of every text pairing it affects
against the WCAG AA floor (4.5:1 for normal text, 3:1 for large), and update
the ratio tables in `README.md` and the guide page with the measured values.
