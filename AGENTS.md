# AGENTS.md

## Purpose
This repository is built for agent-assisted development with many moving parts.
The goal is to ship quickly for a hackathon while keeping quality high enough for
open-source collaboration.

## Core Principles
- Keep changes focused, minimal, and reviewable.
- Favor clarity over cleverness in code, docs, and commit messages.
- Optimize for fast iteration without sacrificing reliability.
- Leave the repository in a better state after each task.

## Testing Policy (Mandatory)
- Full end-to-end (`e2e`) tests must run for every meaningful change before merge.
- Regression testing is required for every impacted flow, module, or integration.
- New fixes must include a test that would fail without the fix when feasible.
- If tests are flaky or failing, treat that as a blocker and resolve or document a
  clear temporary mitigation before proceeding.
- When reporting completion, include what was tested and what risks remain.

## Multi-Agent Workflow Policy
- Prefer multi-agent spawning by default when work can be split safely in parallel.
- Split tasks by clear ownership boundaries (feature area, file set, or subsystem).
- Use one agent to integrate, cross-check, and resolve conflicts after parallel work.
- If a task is tightly coupled and parallelism adds risk, keep it single-agent and
  document why.

## Troubleshooting and Research Policy
- If behavior is broken or unexpected, reproduce it and isolate the failure first.
- Research similar issues online (official docs, issue trackers, community posts)
  before attempting speculative fixes.
- Prioritize proven solutions that match project versions and stack details.
- Validate externally sourced fixes locally before applying broadly.
- Capture key findings in commit/PR notes so future contributors can retrace logic.

## Sandboxes and Component Validation
- For complex or risky changes, create a sandbox to test components independently.
- Use sandboxes to confirm assumptions, debug faster, and reduce blast radius.
- Keep sandbox scope tight: one concern per sandbox when possible.
- Promote only validated behavior from sandbox experiments into production paths.

## Open-Source + Hackathon Standards
- Assume the codebase will be read and extended by external contributors.
- Keep setup and usage straightforward; prefer explicit documentation.
- Avoid secrets or environment-specific assumptions in tracked files.
- Choose maintainable, pragmatic solutions over over-engineered designs.
- Favor delivery speed, but not at the cost of broken core workflows.

## Git Conventions
- Default branch: `main`
- Feature branch prefix: `codex/`
- Prefer small commits with descriptive messages tied to behavior changes.

## Definition of Done
A task is done only when all of the following are true:
- Implementation is complete and scoped correctly.
- Full `e2e` tests pass.
- Regression checks for impacted areas are complete.
- Any breakage investigation included online research when relevant.
- Sandbox validation was used where complexity warranted it.
- Results, tradeoffs, and residual risks are documented clearly.

## Notes
Update this file as project conventions evolve.
