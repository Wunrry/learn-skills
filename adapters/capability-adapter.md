# Capability Adapter

An adapter maps this repository's portable capability contracts to one host's tools and output conventions. Keep this layer outside `teach` and `visualize`.

## Mapping table

| Contract | Host implementation | Required observable result |
| --- | --- | --- |
| Goal discovery | open chat question, form, or UI dialog | learner response is available before scope is fixed |
| Graded check | quiz tool, evaluator, or conversation | answer is withheld until commitment and feedback is returned |
| Research | web search, local corpus, or researcher role | claim, scope, date, evidence, and uncertainty are distinguishable |
| Delegation | sub-agent call, worker, or main-agent role switch | bounded brief and completion result are returned |
| Render and inspect | Mermaid/SVG/plot renderer plus image view | rendered artifact was inspected, not merely generated |
| Persist | Markdown file, note API, or returned text | exact lesson content and media references remain recoverable |

## Adapter rules

1. Preserve the contract's observable behavior even when the interface changes.
2. Keep host-specific names, paths, authentication, and serialization here.
3. Report unavailable capabilities so the core skill can use its fallback.
4. Never report success for a question, citation, render, inspection, or write that did not occur.
5. Keep the lesson output portable; translate to special embeds only at the final host boundary.

## Minimal adapter

A host with no tools can implement all capabilities in conversation:

- ask one open goal question;
- ask graded checks and wait for answers;
- state uncertainty when research is unavailable;
- write diagrams as Mermaid or ASCII source;
- return Markdown for the user to save.

That implementation is intentionally small but still honors the learning and verification contracts.
