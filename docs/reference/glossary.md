# Glossary

This glossary defines the terminology used throughout the Aegis project.

The purpose of this document is to ensure that every architectural discussion, ADR and implementation uses a consistent vocabulary.

## Action

An executable operation requested by the Core.

Actions are carried out by Providers and may succeed or fail.

Examples include stopping a virtual machine, shutting down a host or invoking an external hook.

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

## Provider

A component responsible for executing actions on behalf of the Core.

Providers contain infrastructure-specific logic but never business logic.

## Recorder

A component responsible for persisting events.

Recorders enable auditing, diagnostics and replay.

## Replay

The deterministic reconstruction of a previous execution by processing a recorded sequence of events.

Replay should always produce the same sequence of decisions.

## State

The current position within a workflow.

State is derived from processed events and is never considered the source of truth.

## Workflow

A deterministic sequence of state transitions driven by events.

A workflow describes how the system progresses from one state to another in response to external facts.
