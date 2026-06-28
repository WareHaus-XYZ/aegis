# Glossary

## Action

A request emitted by the Engine describing a side effect to be executed.

The Engine never executes actions directly.

---

## Event

An immutable fact describing something that happened.

Events are the only source of truth.

---

## Workflow

A deterministic sequence of state transitions driven by events.

---

## State

The current execution point of a workflow.

State is always derived from events.

---

## Provider

A component responsible for executing actions on behalf of the Engine.

Providers contain infrastructure-specific logic.

---

## Hook

An external executable invoked by a Provider.

Hooks allow infrastructure integration without coupling the Engine to external systems.

---

## Recorder

A component that persists emitted events.

---

## Replay

The deterministic reconstruction of a previous execution from recorded events.
