# EXP-001｜3countess Commerce Contract Gate

Date: 2026-08-10

## Status

**BLOCKED BY PLATFORM INTERFACE — not a Harness failure**

## Confirmed facts

- External service name: `donix Commerce`.
- Implementation authority: `Zenbu native commerce capability`.
- Product system of record: `Zenbu Native Product DB`.
- Zenbu MCP is connected.
- Current products: 0.
- Current commerce collections: 0.
- Current orders: 0.
- Traveler Journal Charm has no real product / variant mapping yet.

## Runtime contract still unproven

Zenbu MCP has not exposed enough schema / read-back to prove:

- Add-to-cart payload, success response, error response.
- Cart session, persistence, read / update contract.
- Checkout entry, success, cancel, failure contract.
- Production purchase confirmation.
- Unique order ID authority.
- Transaction value authority.

Therefore Core measurement events remain:

- `view_context`: UNKNOWN
- `view_item`: UNKNOWN
- `add_to_cart`: UNKNOWN
- `begin_checkout`: UNKNOWN
- `purchase`: UNKNOWN

## Interpretation

The Agent correctly stopped instead of inferring transaction behavior from capability clues.

This is evidence for the existing `Fail-Closed Unknowns` behavior and creates a new methodology candidate:

### External Capability Boundary Rule

When an external platform / connector cannot expose the contract required by a Frozen Spec, the Agent must:

1. stop inferring runtime behavior;
2. preserve UNKNOWN / DECISION REQUIRED;
3. hand the missing authority to Human / official platform contract sources;
4. continue only work that does not depend on the unresolved contract.

Status: Candidate only; needs another case before promotion to donix Methodology.

## Next actions

### Track A｜Product Truth
Complete the real Traveler Journal Charm product facts and create a real draft product in Zenbu only after Human approval.

### Track B｜Platform contract handoff
Use Human-accessible Zenbu documentation / admin / support / runtime tooling to confirm the cart / checkout / purchase contract. Feed only confirmed contract facts back to the Coding Agent.

## Guardrails

- Do not repeat blind MCP inspection.
- Do not invent cart / checkout contracts.
- Do not switch commerce platform only to unblock EXP-001.
- Do not modify Frozen Spec or C1-approved UI shell.
- Do not mark production-ready until Product Truth and runtime contract are both confirmed.

## Experiment implication

EXP-001 remains `active`.

Harness execution through CONSULT → Spec → UI shell → Human Gate C1 is still valid. The production transaction portion is blocked by an external capability boundary, not by requirement misunderstanding or Agent rework.
