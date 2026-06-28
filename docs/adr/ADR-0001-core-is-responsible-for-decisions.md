# ADR-0001: The Core Is Responsible for Decisions

**Status:** Accepted

## Context

Aegis is intended to automate responses to critical infrastructure events such as power failures while remaining deterministic, testable and infrastructure-independent.

During the initial design phase, multiple architectural approaches were considered. One option was to allow infrastructure-specific components to contain workflow logic or make autonomous decisions. Another option introduced additional orchestration layers responsible for translating decisions into execution plans.

These alternatives increased complexity without solving a concrete operational problem for the initial scope of the project.

## Decision

The Aegis Core is solely responsible for making decisions.

Infrastructure-specific components are responsible only for observing reality or executing decisions.

The architecture is divided into three distinct responsibilities:

-   **Event Sources** observe the external world and report immutable facts.
-   **The Core** evaluates those facts and produces deterministic decisions through explicit state transitions.
-   **Providers** execute the requested actions and report execution results back as new events.

Providers must never alter workflows, introduce business logic, or make autonomous decisions.

Likewise, the Core must never communicate directly with infrastructure.

## Rationale

Separating decision making from execution provides several important properties:

-   deterministic behavior;
-   complete replayability;
-   infrastructure independence;
-   improved testability;
-   simpler providers;
-   easier reasoning about system behavior.

The Core remains entirely unaware of Proxmox, UPS vendors, Linux services or any other infrastructure-specific implementation.

## Consequences

All infrastructure integrations must be implemented as Providers.

Providers translate Core decisions into infrastructure operations and translate execution results into events.

Future integrations must preserve this separation of responsibilities.

If additional orchestration layers become necessary, they must be justified by concrete operational requirements and documented through a new ADR.

## Alternatives Considered

### Intelligent Providers

Providers capable of making workflow decisions.

Rejected because it distributes business logic across multiple implementations and makes behavior harder to reason about.

### Multi-layer Orchestration

Introducing planners, executors or intermediate orchestration layers.

Rejected because the current operational requirements do not justify the additional complexity.

These abstractions may be introduced in the future if supported by real use cases.

## Principles

This decision supports the core principles of Aegis:

-   Simple.
-   Deterministic.
-   Explainable.
