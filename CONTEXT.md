# Learning Skills Context

This repository defines a portable instructional layer for teaching and visual explanation. Its core vocabulary separates policies from the capabilities and roles that a host may use to carry them out.

## Core language

**Core skill**:
A primary, reusable policy that an agent can invoke for a user-facing task, such as teaching or visualizing.
_Avoid_: Runtime plugin, extension

**Subskill**:
A focused behavior contract or role description that a core skill reaches only when a particular branch needs it.
_Avoid_: Mandatory dependency, implementation

**Capability**:
An action the host can provide, such as asking, grading, researching, rendering, delegating, or persisting.
_Avoid_: Tool name, API

**Adapter**:
A host-specific implementation that maps a capability contract to tools, agents, scripts, or a user interface.
_Avoid_: Core skill, teaching rule

**Role**:
A bounded delegated responsibility, such as researcher or diagram author, with a brief and a completion criterion.
_Avoid_: Autonomous feature

**Dependency node**:
A claim or reasoning step in the learner's model, with explicit incoming ideas and a check before dependent material is added.
_Avoid_: Isolated fact, quiz item

**Verified visual**:
A visual whose source has been rendered and inspected for both semantic correctness and readability.
_Avoid_: Rendered file, syntactically valid image
