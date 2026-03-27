# Repository Structure

This repo should be reader-first.

People who land here should see a story surface:

- arcs
- reading orders
- editions
- entry points

They should not need to understand nodes, DAGs, lanes, or canon plumbing just to read.

The machine-readable canon and lore already live in the separate canon repo. This repo should consume that authority without duplicating its full structure.

## Working assumptions

- Canon authority stays upstream in the canon workspace.
- For publication structure, treat `documentation/CPC_Blueprint_v3_4.md` as the current authority.
- Public files here should read like literature, not system metadata.
- Source-node linkage should exist only as thin internal provenance.

## Design principles

- Organize public prose by reading experience, not by node.
- Make arcs the main browsing surface.
- Treat arcs as character-centric threads by default.
- Make reading order explicit for new readers.
- Keep editions separate from live arc reading.
- Preserve source provenance quietly in internal manifests.

## Recommended tree

```text
README.md
arcs/
  README.md
reading-orders/
  README.md
editions/
  README.md
.editorial/
  README.md
  inbox/
    README.md
    .gitignore
    intake.template.yml
  indexes/
    README.md
    characters/
      README.md
    events/
      README.md
    devices/
      README.md
  source-map.template.yml
  section.template.md
docs/
  repository-structure.md
  editorial-workflow.md
  inbox-protocol.md
```

## Public surface

### `README.md`

This is the landing page for readers.

It should answer:

- what this repository is
- how to start reading
- whether reading is linear or nonlinear
- where arcs and editions live

### `arcs/`

This is the primary reading surface.

A reader should be able to open an arc folder and just read.

Recommended shape:

```text
arcs/
  lia/
    README.md
    01-ground-state.md
    02-pressure.md
  ava/
    README.md
    01-threshold.md
```

Inside each arc:

- `README.md` explains the arc
- numbered section files hold the prose in reader order

Those section files can each be larger than a canon node. They are publication sections, not canon atoms.

Arc rule:

- each public section should have one primary arc
- other character threads can converge into that section without taking over its arc identity

### `reading-orders/`

This tells readers how to move through a nonlinear work.

Use this for:

- start-here guidance
- “core path” order
- alternate arc-first orders
- spoiler-aware orders

`release-order.md` should only include sections that are actively part of the current guided release path.
Not every public arc section needs to appear there immediately.

### `editions/`

This holds assembled experiences:

- omnibus reads
- novel cuts
- special release versions
- print-oriented builds

`arcs/` is the live browseable story surface. `editions/` is the packaged version.

## Internal surface

### `.editorial/`

This is where you keep the minimum internal machinery needed to maintain the public text responsibly.

Keep only lightweight metadata here:

- which canon ref a section came from
- which source nodes feed a published section
- notes about merges, bridges, or omissions
- sequence manifests for internal assembly
- interpretation ingress and classification records
- extracted indexes for reusable story entities

This layer exists for maintenance, not for readers.

### `.editorial/inbox/`

This is the ingress layer for polished interpretation prose that has not been mapped yet.

What belongs here:

- polished novelized passages derived from canon
- interpretation drafts from agents or humans
- candidate bridge prose
- candidate composite sections that may become public arc sections

What does not belong here:

- reader-facing finalized prose
- raw canon exports
- machine-readable canon truth

The inbox should be gitignored for content so temporary drops, intermediate analyses, and routing noise do not pollute repository history.

### `.editorial/indexes/`

This is the committed extraction layer for durable story metadata used by the publication process.

Recommended index families:

- characters
- events
- devices

These indexes are useful when the agent needs to determine:

- which characters appear in an interpretation
- which significant events are referenced or transformed
- which plot devices or systems are active
- whether a section belongs to a known convergence cluster
- which secondary character arcs converge inside a primary arc section

This data should be derivative and publication-focused. Canon authority still remains upstream.

## Why this shape fits CPC better

The canon repo is already responsible for:

- machine-readable structure
- node identity
- track metadata
- lifecycle state
- continuity rules

So this repo should not repeat that architecture as its main public interface.

Instead:

- canon stays node-first upstream
- publication becomes arc-first here
- provenance survives in a hidden editorial layer

That gives you a repo you can confidently send to readers without losing the ability to trace and rebuild sections later.

## Practical guidance

- Prefer one prose file per published section, not per source node.
- Keep sections comfortably readable on GitHub.
- Use numeric prefixes inside arcs only for local reader order.
- Give each section one primary arc, then record convergence from other arcs in `.editorial/`.
- Record source-node provenance in `.editorial/`, not in public prose unless needed.
- Treat `release order` as a scheduled reader path, not an automatic list of every public section.
- Treat editions as curated packages, not the default browsing surface.
- Treat `.editorial/inbox/` as transient ingress, not archival storage.
- Promote stable extracted metadata from inbox analysis into `.editorial/indexes/`.
