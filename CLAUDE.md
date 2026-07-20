# CLAUDE.md: JSC Workshop website

This repo is the public website for JSC Workshop, Jordan's one-person
custom software business. It deploys to GitHub Pages at
jscworkshop.co.uk. Read this before editing anything.

## Architecture rules

- ONE self-contained file: index.html. All CSS and JS stay inline.
  No build step, no frameworks, no npm. This is deliberate: the site
  is itself a demonstration of simple tools done properly.
  The single agreed exception is og.jpg, the 1200x630 social share
  card, because link crawlers will not accept an SVG or a data URI
  and need a real file at an absolute URL. Images may live beside
  index.html. Code and styles may not.
- No analytics, no trackers, no external requests except Google Fonts.
- Must work with JavaScript disabled (content readable, reveal
  animations simply don't run). Respect prefers-reduced-motion.
- Light and dark mode both supported via CSS variables. Test both.

## Voice rules (locked, from the brand system)

- British English. NO em dashes anywhere, ever.
- Plain, calm, warm. Nothing cheesy, no consultant-speak, no buzzwords.
- Banned words in copy or naming: Tech, Digital, Solutions,
  Consulting, AI, Labs.
- The training tracker is always "one example", never the identity.
- Solo-inclusive phrasing: never "your team" alone; the audience runs
  from one person with a van to a hundred on a shop floor.
- Illustrative figures stay labelled honest ("Typical time lost").
  Never imply client results that don't exist.

## Brand marks (do not mix these up)

- The full seal (double ring, diamond finials, ticks, JSC with
  WORKSHOP inside) is the logo. It appears in the header, stamped on
  the bio letter, and on og.jpg. Anywhere the mark shows at a
  visible size, use the full seal.
- The favicon alone uses a heavy ring with "JC", because three
  letters are unreadable at 16px. Do not "fix" it to JSC.
- The letterforms in the inline SVGs are baked path outlines taken
  from IBM Plex Serif and IBM Plex Mono, not live text, so the mark
  never depends on a font loading. Regenerating them needs Python
  fontTools; keep the paths as they are unless the mark changes.

## Current state and known placeholders

- Contact email is LIVE: jordan@jscworkshop.co.uk (Google Workspace
  on the .co.uk domain, wired 2026-07-20). If it ever changes, it
  appears in THREE places that must change together: the visible
  contact-row text, the mailto: href on that row, and the EMAIL
  const in the job-sheet script. Search for jscworkshop.co.uk
  mailto/EMAIL usages to find them all.
- The phone row is PARKED: removed from the contact panel (an HTML
  comment marks the spot) until the real number exists. When it does,
  reinstate the row as a tel: anchor like the rows beside it. Never
  publish placeholder digits.
- The shop-door sign is driven by the data-capacity attribute on
  <body>: "open" / "waitlist" / "closed". Edit that one value and
  nothing else. All three sets of copy live in the markup and CSS
  shows only the matching one, so the sign stays truthful even with
  JavaScript off. When closed, check the return month named in the
  closed copy (currently September) is still right.
- The Pseudonymiser section links to the live tool at
  https://pseudonymiser.jscworkshop.co.uk/; keep that URL in sync if
  it moves.
- The 90-second demo film does not exist yet. The example section
  says a demo is on its way; swap that line for a real link once the
  film is made. Never link a demo that is not real.

## Deployment

GitHub Pages from main branch root. CNAME file must contain
jscworkshop.co.uk and must not be deleted. Test locally by opening
index.html in a browser before pushing; there is no staging.
