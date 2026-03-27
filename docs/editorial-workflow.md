# Editorial Workflow

This workflow assumes the canon repo is the source of truth and this repo is the public reading surface.

## 1. Pin the canon source

Before writing or updating public prose:

- note the canon repo path or URL
- note the ref or commit
- note the blueprint authority used
- note the source files consulted

Record that in `.editorial/source-map.yml`.

## 2. Ingest polished interpretation prose through the inbox

When a polished interpretation lands from upstream canon work, place it in `.editorial/inbox/`.

Each inbox item should get an intake manifest that captures:

- source file and arrival date
- whether the text is direct render, composite, bridge, or alternate interpretation
- primary arc and any converging arcs
- candidate canon nodes
- inferred tracks, characters, devices, and events
- inferred lane, waveform, entropy, and convergence role
- continuity questions or contradictions
- recommended routing destination

The inbox is the staging area where the agent answers:

- what part of canon this belongs to
- which character thread owns the section
- which other character threads converge into it
- what it is doing structurally
- who and what it contains
- whether it should become a public section, be split, be merged, or be held
- whether it should enter `release order` now or stay public-but-unscheduled until later

## 3. Decide the reader-facing destination first

Write with the public destination in mind:

- an arc section
- a reading-order guide
- an assembled edition

Do not begin from internal atomization unless it materially helps the release.

## 4. Publish into arcs, not nodes

The default output unit in this repo is a reader-facing section.

A section may map to:

- one canon node
- several canon nodes merged together
- a bridge written to smooth transitions

The public file should optimize for readability on GitHub, not for canon atom purity.

Publication and release scheduling are separate decisions:

- promotion decides whether the prose becomes a public section under `arcs/`
- release scheduling decides whether that public section is added to `reading-orders/release-order.md` now
- a section may be public in `arcs/` while remaining out of `release order` until its intended release window

Publication rule:

- every section belongs to one primary arc
- convergence with other arcs is recorded in `.editorial/`, not solved by giving the section multiple owners

## 5. Keep provenance thin and private

For each public section, record in `.editorial/`:

- public path
- source nodes
- source canon paths
- notes on merges, bridges, or cuts

That is enough to preserve maintainability without exposing machinery to readers.

## 6. Maintain derivative indexes

When inbox analysis stabilizes, promote reusable facts into `.editorial/indexes/`.

Maintain at least:

- character records for recurring cast detection
- event records for significant occurrences and cross-arc references
- device records for important systems, tools, artifacts, or mechanisms

Only store publication-useful derivatives here. Do not recreate the entire lore repo.

After the relevant facts have been extracted and the prose has been routed, move the ingress files out of the live inbox and into `.editorial/inbox/.processed/` unless they should be discarded entirely.

## 7. Use reading orders to handle nonlinearity

Because the work is nonlinear, readers need explicit guidance.

Keep that guidance under `reading-orders/`:

- first-read path
- arc-by-arc path
- alternate entry points
- spoiler-aware routes

The reading-order layer is what makes a nonlinear repo readable.

Do not treat promotion as automatic release-order enrollment.

`release order` is the default guided path for material that is meant to be encountered now.
Some public arc sections may remain intentionally unscheduled there until they are ready to be part of that path.

## 8. Assemble editions separately

When you want a novel-shaped or omnibus experience:

- assemble it under `editions/`
- record the sections included
- note the canon ref and editorial assumptions

Editions are packages. Arcs remain the live reading surface.

## 9. Resolve truth upstream

If publication work reveals a canon conflict:

- note it locally
- fix the truth in the canon repo
- then update the public rendering here

This repo should not become a shadow canon store.

## UV handling

If a source node is UV or UV-pending under `v3.4`:

- preserve the Layer 1 contract in `.editorial/`
- do not quietly soften the scene in order to fit an executor
- route full prose execution separately if needed

The public repo can remain reader-first without losing structural integrity.
