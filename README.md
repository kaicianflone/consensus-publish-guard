# consensus-publish-guard

Pre-publish governance for outward-facing content (blog, social, announcements, outbound statements).

`consensus-publish-guard` applies persona-weighted review before content is sent or posted and returns:

- `ALLOW`
- `BLOCK`
- `REQUIRE_REWRITE`

## Why teams use it

Publishing mistakes are expensive: trust loss, policy violations, and legal risk. This guard adds a deterministic quality gate before distribution.

## Core capabilities

- strict schema and unknown-field rejection
- hard-block taxonomy support
- weighted consensus aggregation
- idempotent retries with stable decision replay
- board-native decision + persona artifacts

## Good fit for

- marketing and growth automation
- support or community broadcast workflows
- release announcement pipelines
- AI-generated public responses

## Quick start

```bash
npm i
node --import tsx run.js --input ./examples/input.json
```

## Test

```bash
npm test
```

## Continuous improvement

See `AI-SELF-IMPROVEMENT.md` for ongoing reliability and policy iteration.
