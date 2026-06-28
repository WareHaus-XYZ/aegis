# Aegis Manifesto

Aegis is built on a small set of engineering principles.

These principles are intended to guide every architectural decision, implementation detail and future evolution of the project.

When a new feature conflicts with these principles, the feature must justify the exception—not the other way around.

# Simple

Complexity is introduced only when it solves a real operational problem.

Every abstraction must justify its existence through a concrete use case.

The simplest solution that satisfies the requirements is preferred.

# Deterministic

Given the same sequence of events, Aegis must always produce the same sequence of decisions.

System behavior must never depend on implicit state, execution timing or infrastructure implementation details.

Determinism is the foundation of trust.

# Explainable

Every decision must be understandable.

Operators should always be able to determine why a decision was made and which events produced it.

Behavior should never rely on hidden logic or implicit assumptions.

# Facts Before Assumptions

Reality is represented through immutable events.

Events describe facts that happened.

State is derived from those facts.

# Decisions Before Actions

The Core makes decisions.

Providers execute them.

Business logic belongs exclusively to the Core.

Infrastructure-specific code must never alter workflow behavior.

# Separation of Responsibilities

Every component has a single responsibility.

The Core decides.

Providers execute.

Event Sources observe.

Recorders persist.

No component should assume responsibilities that belong to another.

# Practical Engineering

Aegis exists to solve real operational problems.

The project evolves through practical experience rather than hypothetical requirements.

Architectural flexibility is valuable only when it supports real-world needs.

# Long-Term Thinking

Architecture should enable future evolution without requiring premature abstraction.

The project grows incrementally.

Capabilities are added when operational requirements demonstrate their necessity.

# Trust

The purpose of Aegis is not to prevent failures.

Failures are inevitable.

Its purpose is to ensure that infrastructure responds predictably, consistently and transparently when failures occur.

Trust is earned through simplicity, determinism and explainability.
