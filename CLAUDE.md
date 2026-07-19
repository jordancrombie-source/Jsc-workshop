# CLAUDE.md: JSC Workshop website

This repo is the public website for JSC Workshop, Jordan's one-person
custom software business. It deploys to GitHub Pages at
jscworkshop.co.uk. Read this before editing anything.

## Architecture rules

- ONE self-contained file: index.html. All CSS and JS stay inline.
  No build step, no frameworks, no npm. This is deliberate: the site
  is itself a demonstration of simple tools done properly.
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

## Current state and known placeholders

- Contact email and phone are PLACEHOLDERS (hello@example.co.uk and
  the EMAIL const in the job-sheet script). Swap to the real
  hello@jscworkshop.co.uk address when mail forwarding is live.
- CAPACITY const controls the shop-door sign: "open" / "waitlist" /
  "closed". REOPEN names the return month when closed.
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
