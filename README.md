# Agent Policy Repository

This repository defines a strict execution specification for an autonomous software engineering agent.

## Purpose

The `SPEC.md` file is the single source of truth defining how the agent must behave when generating or modifying code.

It enforces:

- deterministic behavior
- explicit decision-making
- minimal and controlled changes
- strict testing requirements
- language-specific engineering conventions

## Scope

The specification applies to all supported environments and runtimes, including but not limited to:

- VS Code extensions
- CLI-based agents
- LLM coding tools (e.g., Claude Code)
- CI/CD automation agents

Runtime-specific behavior may be layered on top of the core specification, but must never override it.

## Key Principles

- No implicit decisions
- No ambiguity tolerance
- No uncontrolled creativity
- No external dependencies unless explicitly requested
- All uncertainty must result in a binary clarification question

## Testing Policy

Tests are treated as executable specifications:

- no placeholder or dummy values
- randomized data must use UUID v4 (strings)
- numeric randomness must use cryptographically secure generators
- tests must cover:
  - normal behavior
  - edge cases
  - failure cases

## Language Constraints

The specification enforces strict conventions for:

- Java
- Go
- Docker

Each language section prioritizes consistency, explicitness, and maintainability over stylistic flexibility.

## Repository Structure

- `SPEC.md` → core behavioral specification (authoritative)
- `runtimes/` → optional environment-specific overrides (non-authoritative)

## Authority Model

In case of conflict:

1. SPEC.md has absolute precedence
2. Runtime rules are secondary
3. Local project rules are tertiary

## Goal

Ensure predictable, reproducible, and production-grade software engineering behavior from autonomous agents.
