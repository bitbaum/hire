# hire

**The page moved to <https://bitbaum.orangecat.ch/hire/>.** This repository now
serves a redirect so that links already in the world keep working.

## Why it moved

It was the destination of the primary button on every page of
bitbaum.orangecat.ch, and it looked like a different company: its own light
theme and typeface, a personal name in the title, a superseded GitHub handle in
the footer, and no way to make contact — a prospect's only link was a profile
page. A hire page that a visitor cannot reply to is not a hire page.

It now lives inside the site it belongs to, in the same design system, with the
same header and footer, and with an address you can write to. The live-work
list is still derived rather than typed — the same rule that made it worth
generating here applies there, and the generator is now
`bitbaum/bitbaum` `site/build.mjs`, reading the fleet map.

## What used to be here

`build.mjs`, `work.json`, `register.snapshot.json` and the weekly
`sync-work.yml` workflow existed only to produce `index.html` from the fleet
register. With the page gone they have no artifact to build, and the workflow
would have committed the old page back over this redirect within a week, so
they were removed rather than left to rot. They are in this repository's git
history if the approach is ever wanted again.
