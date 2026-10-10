# Agent workspace

This folder contains shared, public-safe working guidance for human and AI agents contributing to the Millenova public engineering facade.

It is intentionally separate from product documentation. Files here define **how agents should work**, review, format and publish material in this repository.

## Required reading

Before editing public documentation, agents should read:

1. [`../WHAT_IS_PUBLISHED_HERE.md`](../WHAT_IS_PUBLISHED_HERE.md) — publication/security boundary.
2. [`../MILLENOVA_PUBLIC_FACADE_IMPLEMENTATION_PLAN.md`](../MILLENOVA_PUBLIC_FACADE_IMPLEMENTATION_PLAN.md) — review-first publication programme.
3. [`MERMAID_GRAPH_GUIDE.md`](MERMAID_GRAPH_GUIDE.md) — reusable Mermaid rules for GitHub-safe diagrams.

## Working principle

```text
private Millenova evidence
        ↓
agent audit / draft
        ↓
public-safe artifact
        ↓
Wilder review
        ↓
correction / approval
        ↓
public repository
```

Agents must not treat the private implementation repository as an automatically publishable mirror.

## Shared guidance currently available

| Guide | Purpose |
|---|---|
| [`MERMAID_GRAPH_GUIDE.md`](MERMAID_GRAPH_GUIDE.md) | Prevent cropped Mermaid labels and keep diagrams readable, reusable and technically dense on GitHub |

## Adding future agent guidance

New files may be added here when a repeatable implementation, review or publication lesson is discovered.

Good candidates include:

- documentation review checklists;
- public-disclosure checks;
- diagram conventions;
- status vocabulary;
- evidence-grounding rules;
- screenshot redaction rules;
- public engineering-log conventions.

The folder should remain concise: preserve **reusable process knowledge**, not temporary scratch notes.
