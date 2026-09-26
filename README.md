> **Moved.** These assets now live in one repo, split by project:
> https://github.com/souvikb93/framer-assets
>
> This repo is kept so the old Pages URLs keep resolving and so the
> `pre-type-scale` / `type-scale-v1` rollback tags stay reachable.
> **Edit the monorepo, not this one.**

# Streamliner — synthesis

Four findings resolving into three opportunity areas. One self-contained HTML
file, no build step, no dependencies beyond the Uncut Sans webfont from jsDelivr.

**Live:** https://souvikb93.github.io/streamliner_synthesis/

**Framer node:** `k567uewrD` on `/projects/streamliner`

## Using it in Framer

Embed node → **URL** mode → paste the live URL → set **Height to Fixed, 610**.
URL embeds cannot auto-measure; the file locks its own desktop height with
`@media (min-width:900px){body{min-height:610px}}` so the two agree.

## How it reads

The chain builds one beat at a time: a finding lights, a connector draws from it,
the insight it feeds scales up and lights, then its opportunity area follows.
Connectors are never idle — they are drawn only on the step that uses them, so
the space between the bands stays empty until something crosses it.

Connector channels are biased into the gap above each band label
(`y1 + 26 + (u-1)*16`) so a line never crosses a word.

## Constraints

- **Fixed desktop height** — Framer measures the embed document and writes the
  value back to the node, so a document that changes height makes the page jump.
- **Responsive inside the file** — Framer's M (810) and S (390) breakpoints are
  zero-override replicas of L (1200) and share one node height.
- **Reduced motion respected** — the chain appears without animating; nothing is
  hidden behind a transition.
- **No all-caps labels**, 4.5:1 contrast floor on every piece of text.

Shared design rules for every asset in this case study:
https://github.com/souvikb93/streamliner-final
