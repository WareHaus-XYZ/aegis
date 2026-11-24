# Glossary

This glossary defines the terminology used throughout the Aegis project.

The purpose of this document is to ensure that every architectural discussion, ADR and implementation uses a consistent vocabulary.

## Action

An executable operation requested by the Core.

Actions are carried out by Providers and may succeed or fail.

Examples include stopping a virtual machine, shutting down a host or invoking an external hook.

## Business Logic

The rules that determine how a workflow responds to events: which decisions are made in each state and which actions they request.

Business logic belongs exclusively to the Core.

Event Sources, Providers and Recorders contain only the infrastructure-specific code needed to observe, execute or persist.

## Core

The deterministic decision-making component of Aegis.

The Core consumes events, evaluates the current state and produces decisions.

The Core never interacts directly with infrastructure.

## Decision

A deterministic conclusion reached by the Core after processing one or more events.

Decisions determine the next state of the workflow and may result in one or more actions.

## Event

An immutable fact representing something that happened.

Events describe observations of reality or execution results.

Events are the only source of truth consumed by the Core.

## Event Source

A component responsible for observing external systems and translating observations into events.

Examples include UPS monitors, timers and manual triggers.

## Execution Result

An event reported by a Provider that describes the outcome of an action.

Execution results are consumed by the Core like any other event.

## Provider

A component responsible for executing actions on behalf of the Core.

Providers contain infrastructure-specific logic but never business logic.

## Recorder

A component responsible for persisting events.

Recorders enable auditing, diagnostics and replay.

## Replay

The deterministic reconstruction of the Core's states and decisions from a recorded sequence of events.

Replay must always produce the same sequence of decisions.

Replay never sends actions to Providers and never consumes live events. The outcomes of actions are taken from the recorded execution results.

## State

The current position within a workflow.

State is derived from processed events and is never considered the source of truth.

## Traceability

The ability to follow every decision back to the events that produced it, and every action forward to its execution result.

Traceability relies on the recorded sequence of events, decisions, actions and execution results.

## Workflow

A deterministic sequence of state transitions driven by events.

A workflow describes how the system progresses from one state to another in response to external facts.
