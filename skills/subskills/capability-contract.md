# Capability Contract

The main skills name behaviors, not products or tool APIs. A host can satisfy a behavior with a native function, another agent, a script, or ordinary conversation.

## Capability vocabulary

**Goal discovery** finds the learner's intended outcome, context, depth, and constraints. It is open-ended and has no answer key.

**Graded check** asks a question with a known answer or evaluates a prediction, explanation, or application. It is used to map prerequisites and confirm a dependency node.

**Research** verifies facts, definitions, formulas, dates, current behavior, and other claims whose correctness cannot be trusted from memory alone.

**Delegation** hands a bounded role to another agent or process, with a brief, input contract, and completion criterion.

**Render and inspect** turns a visual source into something visible and checks both its semantics and its presentation.

**Persist** writes a durable record in ordinary Markdown while preserving order, code fences, equations, links, and media references.

## Fallback rules

- Without goal discovery, ask one clear open question in the conversation and wait.
- Without a graded-check tool, ask the question in Markdown and withhold the answer until the learner responds.
- Without research, narrow the claim, state uncertainty, and avoid using it as an unquestioned foundation.
- Without delegation, perform the bounded role yourself if the required inputs and verification are available.
- Without a renderer, provide a source visual with alt text and mark it unverified.
- Without persistence, return clean Markdown that the host can save; never claim that it was stored.

The fallback preserves the behavior's contract, not its user interface. Do not mention an unavailable tool as if it ran.
