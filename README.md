# hire

The one-pager at <https://bitbaum.github.io/hire/> — fractional CTO / contract
engineering, Zürich.

## The "Live work" list is generated

Everything between the `WORK:START` / `WORK:END` markers in `index.html` is
produced by `build.mjs` from the fleet register
(<https://fleetcrown.orangecat.ch/api/fleet/register>). **Do not edit it by
hand** — the next build overwrites it, and CI fails the PR that tried.

```bash
node build.mjs            # fetch the register, rewrite index.html
node build.mjs --offline  # build from register.snapshot.json
node build.mjs --check    # exit 1 if the page is out of sync
```

`work.json` is the editorial half: which systems appear, in which group, under
what name, with what sentence. The register owns where each one currently
lives. Neither owns the other's half.

## Why it is generated

It used to be typed, and on 2026-09-12 it carried four defects at once:

- it linked `revampit.orangecat.ch`, a host retired on 2026-09-10;
- it listed **RevampIT and evig as two separate systems** — the organisation
  renamed, so that is one system counted twice, to a reader counting systems;
- it named the clinic "VitaReBa", replaced by "Vita";
- it named the housing product "AOZ Wohnen", which is neither its current name
  (AOZ Begleitung) nor the retired one on record.

None of them broke anything: a retired host answers 200 because it is a
permanent redirect. That is exactly why nothing reported them.

`build.mjs` refuses to build rather than repeat any of it — an unknown slug, a
missing URL, an unknown group, or **two entries resolving to the same host**
each fail the build with the offending name.
