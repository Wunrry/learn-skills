# Learning Skills

A runtime-neutral learning system for agents that should help people build understanding rather than collect disconnected facts.

The repository keeps two primary skills:

- [`teach`](./skills/teach/SKILL.md) turns a learning request into a calibrated, motivated lesson.
- [`visualize`](./skills/visualize/SKILL.md) adds a visual only when structure, direction, or geometry is clearer as a picture.

The original system was built for a specific agent runtime. This repository keeps its teaching method while replacing runtime-specific tools with capability contracts and Markdown-compatible fallbacks.

## Repository shape

```text
skills/
├── teach/SKILL.md
├── visualize/SKILL.md
└── subskills/
    ├── capability-contract.md
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

`teach` and `visualize` are the reusable policies. The files in `subskills/` describe optional roles and capabilities. A host may implement those capabilities with native tools, agents, scripts, or plain conversation.

## Using the skills

Give the host the relevant `SKILL.md` as its active instruction. A host that supports skill discovery can expose both skills by their frontmatter names. A simpler host can load `teach` directly and follow its links when a branch requires research, quizzes, or visuals.

There are no required runtime dependencies. The minimum useful implementation is a conversation that can ask questions, wait for answers, and write ordinary Markdown. Rendering, web research, delegated roles, and persistent logs are optional capabilities.

## Design rules

1. Keep pedagogy independent from its transport, UI, renderer, and storage.
2. Treat a capability as a contract with a fallback, not as a named tool.
3. Preserve the dependency graph: foundations, motivated derivations, and checks stay connected.
4. Prefer a correct plain-text or source-format visual over an unverified image.
5. Keep the learner's goal, current level, and requested depth visible throughout the session.

## Provenance

The method was extracted from the Pi-oriented `learn` project. Pi extensions and Obsidian-specific behavior remain in that project; this repository is the portable instructional layer.
