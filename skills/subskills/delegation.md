# Delegation and Orchestration

Use delegation to keep the teaching agent focused on the learner. The main agent remains the **orchestrator**: it owns the goal, level calibration, dependency plan, explanation, interaction, and final decision. A delegated child owns one bounded production task and never takes over the lesson.

## Role boundary

| Role | Child owns | Main agent owns |
| --- | --- | --- |
| `researcher` | Search, source evaluation, synthesis, and uncertainty report | Whether the claim matters, how it enters the dependency graph, and how it is explained |
| `mermaid-maker` | Relationship-diagram source, rendering, and visual inspection | Whether a visual is warranted, the concept brief, and whether the artifact teaches the intended relationship |
| `svg-maker` | Spatial-diagram source, rendering, and geometric inspection | Whether a visual is warranted, the geometry brief, and whether the artifact teaches the intended geometry |

The child receives enough context to work in isolation. It does not address the learner, change the lesson goal, invent missing requirements, or silently return an unverified result.

## Dispatch protocol

1. **Choose one bounded job.** State the exact claim or visual idea, scope, constraints, and why the result is needed.
2. **Write a task packet.** Include relevant learner context, the decision the result supports, required evidence or verification, and the return format.
3. **Dispatch the named role.** Use the host's sub-agent mechanism, worker process, or an equivalent isolated context. Do not encode a particular API in the teaching skill.
4. **Wait for the result.** The main agent keeps the learner-facing thread focused and does not pretend the child has finished.
5. **Validate the return packet.** Check status, scope, evidence or inspection, and unresolved caveats before using it.
6. **Integrate selectively.** Translate the result into the learner's dependency graph. Preserve citations and uncertainty; do not paste a research dump or maker transcript into the lesson.
7. **Recover explicitly.** On `partial`, `blocked`, timeout, missing evidence, or failed rendering, narrow the task, retry once when useful, or follow the capability fallback. Never upgrade an incomplete result to verified.

## When to dispatch

- For a substantial or multi-step lesson, dispatch `researcher` before finalizing the dependency plan. The child maps the field; the main agent chooses the teaching path.
- Dispatch `researcher` whenever a claim is uncertain, niche, current, high-stakes, numerical, or version-dependent.
- When `visualize` decides a visual materially improves the lesson and a maker role is available, dispatch exactly one suitable maker for that visual.
- Keep learner interaction in the main agent. Goal questions and graded checks require the live learner context and should not be handed to a research or visual child.

For a short, stable explanation, skip delegation and state that no external verification was needed. This is a deliberate scope decision, not an assumption that every task is complete.

## Return packet

Every child returns a compact, machine-readable-in-spirit packet:

```text
STATUS: complete | partial | blocked
ROLE: researcher | mermaid-maker | svg-maker
SUMMARY: one short paragraph
RESULT: the findings or artifact reference
EVIDENCE: citations, source identifiers, or inspection notes
CAVEATS: scope, uncertainty, or missing requirements
NEXT: integrate | retry | fallback
```

The main agent may ask for a correction when a required field is missing. A child that cannot satisfy the brief returns `blocked` or `partial`, with the reason, instead of fabricating a successful result.
