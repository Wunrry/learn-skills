---
name: visualize
description: Add a correct, minimal visual when a lesson is clearer as a diagram, spatial picture, graph, sequence, state machine, comparison, or other representation of structure.
---

# Visualize

Use a picture to expose structure that prose would make harder to see. A visual earns its place when it shows shape, direction, containment, sequence, dependency, or geometry; it is not decoration and it should not merely repeat a sentence.

Use the portable capability and fallback rules in [`../subskills/capability-contract.md`](../subskills/capability-contract.md).

The main agent decides what the learner needs to see. When a maker role is available, dispatch the bounded visual-authoring task so the main agent can stay with the teaching plan and learner interaction. Use [`../subskills/delegation.md`](../subskills/delegation.md) for the handoff and return packet.

## Decide whether a visual is warranted

Ask:

- Is the central idea a relationship, system, flow, hierarchy, sequence, state change, comparison, or spatial arrangement?
- Would the learner understand the dependency or geometry faster from a picture?
- Can one small visual carry the idea without a dense legend?

If the answer is no, keep the explanation in prose, equations, or a small table. A missing visual is cheaper than a false or distracting one.

## Choose a representation

Select the simplest representation that preserves the relevant structure. Dispatch one suitable maker per visual when the host supports delegated roles; other renderers and authoring methods are valid when they satisfy the same contract:

- **Nodes and relationships:** Mermaid, graph syntax, a flowchart, a dependency map, or a plain-text graph. The delegation protocol routes this work to a relationship-diagram maker when one is available.
- **Positions and shapes:** SVG, a plotted image, coordinate geometry, a number line, or another precise drawing. The delegation protocol routes this work to a spatial-diagram maker when one is available.
- **Small, simple comparisons:** Markdown table, aligned text, or a compact annotated equation.
- **No renderer available:** provide the source in a fenced block plus a concise description and alt text. State that it has not been pixel-verified.

Do not choose a renderer because it is familiar. Choose it because its representation matches the claim.

## Brief the author

Before authoring, reduce the idea to one sentence and the fewest carrying elements. Give the author:

1. The exact concept the visual must make visible.
2. The elements or nodes that must appear.
3. The relationships, directions, coordinates, or ordering that must be true.
4. The elements to omit because they add no explanatory value.
5. Readability constraints: labels, scale, contrast, and intended display size.

If removing an element leaves the idea unchanged, remove it. A brief with more than roughly seven meaningful elements deserves another pruning pass.

## Author, render, inspect

The preferred author is a delegated role. The main agent supplies a bounded brief; the child authors and inspects the artifact; the main agent validates the returned status and integrates the result. If no delegated role exists, the main agent or host tool may perform the loop directly:

1. Write the complete source or artifact.
2. Render it using an available renderer.
3. Inspect the rendered result, not only the source or a successful exit status.
4. Check semantic truth: arrows, labels, geometry, ordering, and containment say exactly what the brief says.
5. Check presentation: nothing overlaps, clips, crowds, or becomes unreadable at the intended size.
6. Simplify or edit, then render again until the result is correct and clean.

Only call a visual verified when this loop has happened and the return packet records the inspection. If it cannot be rendered or inspected, label it `Verification: unverified` and use a conservative source representation instead.

## Embed the result

Prefer portable Markdown:

```markdown
![Short description of the visual](path/to/verified-image.png)
```

Use a host-specific embed only in an adapter layer. Keep the lesson itself independent of vault names, special link syntax, or a particular save directory. Introduce the visual with one sentence and let it carry the relationship; do not narrate every label redundantly.

For every visual, preserve `Verification`, intended display size, and any geometry or accessibility limitation in the surrounding Markdown or return packet.

## Completion criteria

A visual is complete when it has one clear purpose, contains no unnecessary element, represents the intended relationships or geometry truthfully, is readable at its display size, and is either rendered and inspected or explicitly marked unverified.
