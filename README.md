# Learning Skills

A runtime-neutral learning system for agents that should help people build understanding rather than collect disconnected facts.

The repository keeps two primary skills:

- [`teach`](./skills/teach/SKILL.md) turns a learning request into a calibrated, motivated lesson.
- [`visualize`](./skills/visualize/SKILL.md) adds a visual only when structure, direction, or geometry is clearer as a picture.

The package is policy-level and runtime-neutral. Host loading, capability mapping, and one-shot behavior are defined in [`HOST.md`](./HOST.md).

## Repository shape

```text
HOST.md
skills/
├── teach/SKILL.md
├── visualize/SKILL.md
└── subskills/
    ├── capability-contract.md
    ├── delegation.md
    ├── goal-discovery.md
    ├── quiz.md
    ├── researcher.md
    ├── ask-user-question.md
    ├── markdown-log.md
    ├── mermaid-maker.md
    └── svg-maker.md
adapters/
└── capability-adapter.md
```

`teach` and `visualize` are the reusable policies. The files in `subskills/` describe optional roles and capabilities. A host may implement those capabilities with native tools, agents, scripts, or plain conversation. `CONTEXT.md` is the terminology glossary; it is not an execution specification.

## Using the skills

Load the relevant `SKILL.md` as active instructions and resolve its relative links. Hosts with skill discovery may expose the frontmatter names; other hosts can load `teach` directly and follow links only for the branches they use. See [`HOST.md`](./HOST.md) for the minimum contract.

There are no required runtime dependencies. The minimum useful implementation is a conversation that can ask questions, wait for answers, and write ordinary Markdown. Rendering, web research, delegated roles, and persistent logs are optional capabilities.

## Design rules

1. Keep pedagogy independent from its transport, UI, renderer, and storage.
2. Treat a capability as a contract with a fallback, not as a named tool.
3. Preserve the dependency graph: foundations, motivated derivations, and checks stay connected.
4. Prefer a correct plain-text or source-format visual over an unverified image.
5. Keep the learner's goal, current level, and requested depth visible throughout the session.
6. Keep the main agent learner-facing; delegate research and visual production through bounded, verifiable return packets.

## Provenance

The method was extracted from the [learn](https://github.com/amosblomqvist/learn) project. Runtime-specific extensions are not part of this package.
