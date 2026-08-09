# EXP-001｜3countess Coding Readiness Gate

Status: **READY PACK CREATED / CODING BLOCKED UNTIL REQUIRED FACTS ARE CONFIRMED**

## Purpose
Before Coding, freeze the remaining implementation facts without reopening CONSULT or Spec.

The first Vertical Slice remains:

`Header / Navigation → Homepage → Analog Everyday → Traveler Journal Charm PDP → Add-to-cart / commerce boundary`

## Required readiness documents

1. `product-data/traveler-journal-charm.md`
2. `integration/commerce.md`
3. `integration/measurement.md`

## Readiness rule

Unknown business / product / integration facts must remain `UNKNOWN / TO CONFIRM`.
Coding Agent must not invent values merely to complete UI.

## Current blockers

### B-01｜Traveler Journal Charm publishable product data
Still requires authoritative values for final price, material, dimensions, variants, sellable state, stock / availability, delivery commitment, returns and customer-service information.

### B-02｜Commerce integration boundary
Still requires Human designation / confirmation of:
- product / variant system of record
- price and availability source of truth
- add-to-cart contract
- cart ownership
- checkout ownership
- success / error states
- purchase confirmation source

No platform may be selected by the Agent solely to remove this blocker.

### B-03｜Minimum measurement capability
Core measurement is limited to:
- `view_context`
- `view_item`
- `add_to_cart`
- `begin_checkout`
- `purchase`

Each event capability is recorded as `SUPPORTED / UNSUPPORTED / DEFERRED / UNKNOWN` after the actual implementation environment is inspected.
Absence of advanced analytics must not trigger architecture expansion.

## Coding permission

Coding may begin only when:
- the Frozen Spec remains unchanged;
- the three readiness documents exist;
- every fact required to make the first purchasable path truthful is either confirmed or explicitly marked as a non-publishable placeholder;
- commerce responsibility is designated;
- the Coding Agent understands which unknowns require Human decision rather than invention.

## Scope protection

Still forbidden in the first Coding pass:
- full Collection / PDP implementation for 收藏生活 and Pet Walk EDC
- membership / account
- wishlist
- AI shopping guide
- recommendation engine
- questionnaire
- dashboard
- crawler
- backend rebuild
- platform replacement chosen by Agent
- analytics governance expansion

## Experiment observation

This gate tests whether Human effort can stay on facts and judgment while the Agent handles implementation detail, without reopening approved business decisions.
