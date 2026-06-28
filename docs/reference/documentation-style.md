# Documentation Style Guide

This document defines the writing and formatting conventions used throughout the Aegis project.

Documentation is part of the project's architecture and should be treated with the same level of care as source code.

## Principles

Documentation should be:

-   Clear
-   Concise
-   Consistent
-   Precise
-   Easy to navigate

Every document should answer a single question.

## Document Structure

-   Each document must contain a single H1 (`#`).
-   Major sections use H2 (`##`).
-   Subsections use H3 (`###`) only when necessary.
-   Avoid heading levels deeper than H3.

## Markdown

Prefer standard Markdown whenever possible.

Structure documents using heading hierarchy.

Reserve horizontal rules (`---`) for meaningful content separation rather than visual layout.

Avoid HTML unless standard Markdown cannot express the intended structure.

## Writing Style

Prefer short paragraphs.

Use active voice whenever practical.

Prefer bullet lists over long prose.

Avoid repeating information across documents.

Explain the reasoning behind important decisions, not only the decisions themselves.

## Terminology

Use the terminology defined in `glossary.md`.

Avoid introducing new terms without updating the glossary.

Use the same term consistently throughout the project.

## Diagrams

Prefer Mermaid diagrams.

Diagrams explain structure.

Text explains rationale.

## Philosophy

Documentation should be as simple, deterministic and explainable as the software it describes.
