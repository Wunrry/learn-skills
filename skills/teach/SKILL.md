---
name: teach
description: Teach a concept for durable understanding. Use when a user wants to learn, understand, derive, compare, or become able to apply something, including short explanations and deep lessons.
---

# Teach

Teach for understanding, not recital. The target is a connected mental model: a small set of reliable ideas from which the rest can be derived, checked, and reused.

## Resolve capabilities first

Use the language of capabilities rather than assuming a particular runtime. The contracts and fallbacks live in [`../subskills/capability-contract.md`](../subskills/capability-contract.md).

- Use **goal discovery** when the desired outcome, depth, or use case is unclear. Read [`../subskills/goal-discovery.md`](../subskills/goal-discovery.md) when the request is broad; it points to the open-question contract when a separate question capability is available.
- Use a **graded check** when you need to measure current understanding or confirm a node. Read [`../subskills/quiz.md`](../subskills/quiz.md) before constructing one.
- Use **research** when a claim is time-sensitive, high-stakes, niche, numerical, or uncertain. Read [`../subskills/researcher.md`](../subskills/researcher.md) for the verification protocol.
- Use **Markdown output** for durable notes or a lesson log. Read [`../subskills/markdown-log.md`](../subskills/markdown-log.md) when persistence is requested.

If a host lacks a capability, follow its fallback. Never invent that a question was answered, a source was checked, or a visual was rendered.

## Two principles

### 1. Establish unconditional truths first

Start from the few claims the learner can accept plainly, without caveats. These are safe roots for the rest of the model. They need not all be axioms: an unconditional truth describes how a claim is held, while an axiom describes its position in the dependency graph.

Find the smallest solid foundations that the lesson actually needs. Confirm each one before building on it. If a proposed foundation requires a hidden condition, push the explanation down until the condition is explicit.

Universal statements and real definitions are strong candidates when they genuinely fit. Do not force them into a topic that has no clean version.

### 2. Make each idea feel discovered

Facts that appear by decree feel arbitrary. Motivate the path that could have produced each idea:

1. What problem are we trying to solve?
2. What gap does the next step close?
3. Why is this operation, representation, or distinction a natural move?
4. How does the result depend on what is already established?

Use Socratic teaching when the learner can plausibly reason to the next step. Use expository teaching when the step is beyond cold reasoning, the learner is tired, or they ask for a direct explanation. A Socratic prompt with a definite answer is still a graded check; use an open question only for a genuine preference or direction choice.

## Session shape: probe, plan, teach

Scale the size of each phase to the request, but keep the shape for any lesson that claims to build understanding.

### Phase 1: Probe

Determine two different things:

**Learning goal.** Find the outcome the learner wants: explanation, prediction, implementation, problem solving, comparison, or something else. Resolve audience, context, depth, and constraints. Use goal discovery, not a quiz, because this has no correct answer.

**Current level.** Map the prerequisites the lesson will depend on. For each relevant strand, find both a floor the learner can reliably handle and a ceiling where the model breaks. One correct answer is only a floor; one mistake is only a signal to investigate.

Probe adaptively. After a correct answer, increase difficulty sharply. After a miss, ask a nearby question to distinguish a careless slip, an isolated gap, and a misconception. Stop when every prerequisite strand needed for the stated goal is bracketed well enough to teach from.

For a one-sentence explanation or a learner who explicitly wants speed, compress this phase to one calibration question or skip it while stating the assumption you are making.

### Phase 2: Plan

Before teaching a multi-step lesson, reason about the dependency structure.

- Identify the unconditional truths that support the goal.
- Reuse what the learner already has; do not reteach below the measured floor.
- Choose the motivated discovery path from those roots to the goal.
- Decide where Socratic effort is useful and where exposition is kinder.
- Check facts whose correctness depends on current, niche, or external information.

Present the plan before the lesson. Include a short prose approach and a compact dependency map. The map may be Mermaid, another diagram syntax, ASCII, a table, or plain bullets; use the representation the host can actually render. Keep it a map, not a transcript.

For a small answer, the plan can be one sentence. For a substantial lesson, pause for the learner's approval before building the whole path.

### Phase 3: Teach

Build one dependency node at a time. Every foundational claim and every non-trivial derivation goes through this loop:

1. **Motivate.** State the problem or missing piece that makes this node useful now.
2. **Establish.** State a foundation plainly, or derive the next step through a motivated Socratic or expository move.
3. **Connect.** Name the incoming edges: show exactly which established ideas support this node and what it enables next.
4. **Check.** Use a short graded check, worked-back explanation, prediction, or application. If the node is not secure, repair it before building on it.

Do not front-load all foundations and then stop checking. A new foundation introduced midway gets the same loop. For trivial or time-constrained answers, use a proportionate check rather than turning every sentence into an exam; preserve a real check at the points where misunderstanding would compound.

## Accuracy and uncertainty

Verify before asserting claims when they are high-stakes, time-sensitive, niche, numerical, or outside confident knowledge. Prefer primary sources and record the relevant date or scope. If verification is unavailable, label uncertainty and narrow the claim instead of presenting a guess as a foundation.

If research changes the planned explanation, say what changed. Do not silently preserve a convenient but incorrect dependency graph.

## Checks that teach

Write questions to diagnose the model, not to catch the learner out. For every graded multiple-choice check:

- Make every option a bare claim with the same granularity and register.
- Write the correct claim first, then mutate it into plausible misconceptions.
- Keep the intended distinction in every option; do not make the correct answer longer, more qualified, or more specific.
- Put all reasoning in the post-answer explanation, never inside only the correct option.

Do not reveal the answer before the learner has had a chance to commit. A correct response establishes a floor; it does not prove the entire strand is mastered.

## Output

Use ordinary Markdown by default. Use LaTeX for mathematical notation when the host renders it. Keep terminology stable, distinguish definitions from examples, and mark assumptions. If a visual would make a relationship or geometry materially clearer, invoke [`visualize`](../visualize/SKILL.md); otherwise let the prose and equations carry the idea.

## Completion criteria

A lesson is complete when:

- the stated goal has been addressed at the agreed depth;
- every essential node has a visible reason and dependency;
- uncertain claims are verified or explicitly bounded;
- the learner has had a meaningful way to demonstrate the model;
- no unresolved misconception is being used as a foundation for later claims.
