# Host Contract

This package is portable at the policy level. A host loads a core skill, resolves its relative references, and supplies capabilities when available.

## Minimum interface

The host MUST be able to:

1. load `skills/<name>/SKILL.md` as active instructions;
2. resolve relative Markdown links from the file that contains them;
3. expose learner messages to the main teaching agent;
4. return ordinary Markdown when no renderer, persistence, or child agent exists.

The host SHOULD expose capability status as `available`, `degraded`, or `unavailable`. `degraded` means the capability exists with a documented limitation.

## Capability mapping

| Capability | Required input | Required output |
| --- | --- | --- |
| Goal discovery | open learner question | learner answer or stated assumption |
| Graded check | question and answer key | learner commitment, result, and feedback |
| Research | claim, scope, freshness | supported claim, evidence, caveats |
| Delegation | bounded task packet | structured return packet |
| Render and inspect | visual source and display target | artifact plus inspection status |
| Persist | Markdown content and media references | recoverable record, or explicit failure |

Map named roles such as `researcher`, `mermaid-maker`, and `svg-maker` to host roles when available. Otherwise use the fallbacks in [`skills/subskills/capability-contract.md`](./skills/subskills/capability-contract.md).

## One-shot hosts

If the host cannot pause for another learner turn, present the plan and continue under clearly stated assumptions. Require approval only when the learner requested staged teaching or unresolved scope would materially change the lesson.

## Portable status labels

```text
Verification: verified | partially verified | unverified
Scope: <topic, version, geography, or date>
Assumption: <assumption, if any>
Uncertainty: <known limitation, if any>
```
