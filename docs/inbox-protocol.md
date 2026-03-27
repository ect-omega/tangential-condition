# Inbox Protocol

The inbox is the ingress layer for polished interpretation prose that has not yet been mapped into the public reading surface.

It belongs under `.editorial/inbox/` because it is operational, transient, and not reader-facing.

## Purpose

Use the inbox when prose arrives that is already polished but still needs classification.

Typical examples:

- a novelized rendering of one or more canon scenes
- a merged interpretation spanning several canon nodes
- a bridge passage written to smooth a reading path
- an alternate pass that may be structurally better than the current section

## Placement

Use `.editorial/inbox/`, not `arcs/` and not `editions/`.

Reason:

- the prose is not published yet
- its canonical mapping may still be uncertain
- its structural role may still be unresolved

## Intake package

Each inbox item should include:

- the prose file itself
- one intake manifest based on `.editorial/inbox/intake.template.yml`
- optional sidecar notes if the mapper needs to explain ambiguities

## Inbox hygiene

The live inbox should only contain items that still need work.

After an item is:

- mapped
- promoted
- held for later
- archived

move its local ingress files into `.editorial/inbox/.processed/` or remove them if they no longer need to be kept locally.

This keeps future agent passes from mistaking already-processed drops for new work.

Arc ownership rule:

- one section should have one primary arc
- other characters and tracks may converge heavily inside it
- convergence should be recorded explicitly rather than collapsing the section into a mixed-ownership arc

Release scheduling rule:

- promotion into `arcs/` does not require immediate inclusion in `reading-orders/release-order.md`
- some items should become public arc sections first and remain unscheduled until their release window
- intake notes should state whether release-order enrollment is `include-now` or `defer`

## Minimum fields the agent should determine

For each inbox item, determine as much of the following as possible:

- primary arc
- converging arcs
- candidate canon nodes
- focus tracks
- characters present
- significant events present
- important devices, systems, or artifacts present
- lane emphasis
- waveform phase
- entropy level
- convergence role
- timeline anchor
- continuity risks
- recommended routing
- release-order action

## Recommended routing outcomes

An inbox item should usually end up in one of these buckets:

- `promote-to-arc-section`
- `promote-to-arc-section-and-defer-release-order`
- `split-into-multiple-sections`
- `merge-with-existing-section`
- `hold-for-edition-only`
- `needs-upstream-canon-check`
- `archive`

## Status model

Recommended statuses:

- `incoming`
- `triaged`
- `mapped`
- `promoted`
- `held`
- `archived`

Status handling rule:

- status alone is not enough
- once the intake work is done, clear the live inbox by moving the associated files into `.processed/`

## What to extract into indexes

When the analysis is stable, promote durable derivatives into `.editorial/indexes/`:

- recurring characters
- significant events
- key devices or systems

Do not treat the inbox itself as the long-term registry.

## Canon boundary

Inbox analysis can infer and organize.

It must not silently redefine canon truth. If the interpretation appears to conflict with canon, route the question back to the canon repo and record the uncertainty locally.
