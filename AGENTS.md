# Agent Guide

This repository is the public reading surface for story prose.

## Core rules

- Treat public readability as the top priority.
- Do not model the public repo as a machine-readable canon store.
- Arcs are character-centric threads.
- Each public section has one `primary_arc`.
- Other threads may converge into that section, but do not turn convergence into mixed arc ownership.

## Public structure

- `README.md` is the root landing page.
- `reading-orders/` explains recommended ways to read.
- `arcs/` contains the actual reader-facing prose.
- `editions/` is for packaged or assembled releases.

## Editorial structure

- `.editorial/inbox/` is staging for polished interpretation prose.
- `.editorial/source-map.yml` tracks promoted public sections back to canon sources.
- `.editorial/indexes/` stores durable derivative metadata for characters, events, and devices.

## Promotion workflow

1. Ingest polished prose through `.editorial/inbox/`.
2. Classify `primary_arc`, `converging_arcs`, source nodes, entities, and structural role.
3. Promote accepted prose into `arcs/<character>/NN-title.md`.
4. Update `.editorial/source-map.yml`.
5. Move processed local ingress files from `.editorial/inbox/` into `.editorial/inbox/.processed/`.
6. Update reading-order files if the public path changes.

## Reading-order policy

- `release order` is the current default recommended reading order.
- Alternate orders may be added later, but they are optional overlays unless explicitly adopted as the default.

## Media policy

- Keep media local to the relevant arc when possible.
- Prefer `arcs/<character>/media/` for section-specific images.
- Do not clutter the prose sequence with loose asset files.

## Inbox hygiene

- `.editorial/inbox/` should contain only items that still need agent attention.
- Once processed, local ingress files should be moved into `.editorial/inbox/.processed/` or removed.

## Editing policy

- Preserve existing prose unless the task is to revise it.
- Keep public markdown clean and minimal.
- Keep operational metadata out of public prose files unless it materially helps readers.
