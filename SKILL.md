---
name: consensus-publish-guard
description: Persona-weighted governance for outbound publishing (blog, social, announcements). Prevents unsafe public claims via hard-block checks, weighted consensus, rewrite paths, and board-native audit artifacts.
homepage: https://github.com/kaicianflone/consensus-publish-guard
source: https://github.com/kaicianflone/consensus-publish-guard
---

# consensus-publish-guard

`consensus-publish-guard` protects public-facing content before release.

## What this skill does

- reviews content drafts with persona consensus
- flags policy/legal/sensitive-risk patterns
- decides `APPROVE | BLOCK | REWRITE`
- emits rewrite patch when fixable
- persists decision + persona updates to board artifacts

## Why this matters

Public content creates brand, legal, and trust exposure. Consensus review creates a safer publish gate than single-pass generation.

## Ecosystem role

Uses persona panels from `consensus-persona-generator` and deterministic logic from `consensus-guard-core`, all persisted via `consensus-tools` board primitives.

## Good fit for

- AI-assisted social/media pipelines
- product launch copy checks
- policy-sensitive communications

## Quick start

```bash
node --import tsx run.js --input ./examples/input.json
```

## Tool-call integration

This skill is wired to the consensus-interact contract boundary (via shared consensus-guard-core wrappers where applicable):
- readBoardPolicy
- getLatestPersonaSet / getPersonaSet
- writeArtifact / writeDecision
- idempotent decision lookup

This keeps board orchestration standardized across skills.

## Invoke Contract

This skill exposes a canonical entrypoint:

- `invoke(input, opts?) -> Promise<OutputJson | ErrorJson>`

`invoke()` starts the guard flow, which then executes persona evaluation and consensus-interact-contract board operations (via shared guard-core wrappers where applicable).
