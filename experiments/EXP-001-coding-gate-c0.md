# EXP-001｜Coding Gate C0｜Draft UI Shell

Date: 2026-08-10 Asia/Taipei
Case: 3countess / 三爵

## Decision

**PASS — Draft UI Shell Technical Gate**

This is NOT a Production Gate and NOT the final Human Gate C.

## Reported implementation result

Human-provided execution summary:

- Frozen Spec remained unchanged; checksum and original modification time remained consistent.
- Zenbu MCP connected successfully.
- Three Zenbu pages were created and all remained `draft`:
  - `exp001-home-shell`
  - `exp001-analog-everyday-shell`
  - `exp001-traveler-journal-charm-shell`
- Purchase and measurement adapters fail closed; they do not generate fake transactions or fake events.
- Existing published `home`, `__header__`, `__footer__` were not modified.
- Product count remained 0; navigation count remained 0.

## Technical validation reported

- Node tests: **9/9 PASS**
- Prohibited commercial-claim scan: **0 hits**
- Zenbu document read-back: **3/3 structural match**
- Zenbu runtime errors in recent 60 minutes: **0**
- Frozen Spec: **unchanged**
- Git integration: workspace is not currently a repository, so branch / commit integration is unavailable.

## Remaining UNKNOWN / blockers

1. Traveler Journal Charm real product data:
   - final price
   - material
   - dimensions
   - approved imagery
   - inventory / sellable state
   - fulfillment facts
2. Human-designated commerce authority and cart / checkout / purchase contract.
3. Receiver / implementation contract for the five Core measurement events and purchase de-duplication.
4. Public URL and visual browser QA remain unverified because the browser bridge / DNS was unavailable in this execution.

## Gate interpretation

The output may only be described as:

> **Safe draft UI shell**

It must NOT be described as:
- production-ready
- publicly purchasable
- validated conversion flow
- completed Vertical Slice

## EXP-001 metric status

### Coding after misunderstanding rework
Current observed result: **0 major rework caused by misunderstanding of Frozen business / IA requirements.**

This metric is provisional until Human Gate C and the real commerce path are completed.

### Frozen Spec compliance
**PASS so far.** The Coding Agent did not modify the Frozen Spec.

### No Invented Facts / Fail-closed execution
**PASS so far.** Unknown product / commerce / measurement facts remained unresolved and did not become fake production behavior.

### Scope control
**PASS so far.** Existing published home / header / footer were not modified, and no fake product catalog or navigation was introduced.

## Next Gate

Do NOT expand to the other two product lines yet.

Next work is split into two independent tracks:

### Track A｜Human UI / UX Gate C1
Review the three draft shell pages for:
- brand architecture clarity
- information hierarchy
- Homepage → Analog Everyday → PDP continuity
- whether the product / context relationship is understandable without invented facts
- whether UI choices contradict Frozen Spec

This requires an accessible public preview, browser bridge, or screenshots. Until then, visual acceptance remains `PENDING`.

### Track B｜Production Readiness Facts
Resolve only the facts required to move from shell to real Vertical Slice:
- Traveler Journal Charm publishable product facts
- commerce authority / integration contract
- Core event support status

Do not solve these blockers by adding new systems.

## New reusable candidate

### Fail-Closed Unknowns Rule
When required business or integration facts are unknown, the Agent may continue only on work that is truth-independent. Unknowns must fail closed: no fake transaction, no fake event, no fabricated product fact, and no production-ready claim.

Status: **Candidate** — observed in EXP-001, not yet promoted to formal donix Rule.
