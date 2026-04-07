<p align="center">
  <img src="https://raw.githubusercontent.com/Lucineer/capitaine/master/docs/capitaine-logo.jpg" alt="Capitaine" width="120">
</p>

<h1 align="center">git-coordination-protocol</h1>

<p align="center">A specification for agent coordination using Git's native semantics.</p>

---

You don't need a new message bus. Many agent coordination problems were already solved by Git. This specification defines how to run agent fleets using its existing primitives: branches for proposals, pull requests for answers, merges for consensus, and forks for dissent.

## Purpose
Agent fleets often rebuild coordination primitives from scratch. This project formalizes an alternative: using Git itself as the coordination layer. It works for millions of developers and can work for your agents.

## How It Works
There is no new runtime. The protocol maps agent actions to Git operations:
- An agent with a proposal creates a branch.
- Discussion and review happen through pull requests.
- Agreement is a merge. Disagreement remains a fork.
- The entire history is an immutable audit log.

## Key Aspects
- **No Central Authority:** Any agent can join by forking. No registration or permission is required.
- **Fork-First Design:** Dissent is built-in. Bad proposals cannot block progress; they are simply not merged.
- **Human-Readable:** Use existing tools (`git log`, GitHub UI) to monitor and debug.
- **Offline Capable:** Works without constant network connectivity.

**Limitation:** This approach inherits Git's latency characteristics and is not designed for sub-second, real-time coordination.

## Quick Start
This is a specification, not a library. To use it:
1. Host a Git repository (on GitHub, GitLab, or a local server).
2. Configure your agents to treat this repo as shared state.
3. Implement the basic operations: clone, branch, commit, push, and open/merge PRs.
4. Agents now coordinate through the repository.

Refer to the specification documents in this repository for detailed protocol behavior and examples.

---

This is a research and specification repository, part of the Cocapn Fleet.

<div align="center">
  <br>
  <p>
    <strong>The Fleet</strong> · <a href="https://the-fleet.casey-digennaro.workers.dev">the-fleet</a> · <a href="https://cocapn.ai">cocapn.ai</a>
  </p>
  <p>Attribution: Superinstance & Lucineer (DiGennaro et al.).</p>
</div>