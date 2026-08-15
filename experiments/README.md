# Experiments

Experiments turn Patterns into bounded, reproducible tests.

## Public experiment rules

Public experiments should contain only information that another contributor can inspect, reuse, or reproduce safely.

Do include:

- hypothesis;
- scope and non-goals;
- sanitized or synthetic context;
- agent instructions required for reproduction;
- human approval gates;
- acceptance criteria;
- result and evidence;
- Adopt / Reject / Continue decision.

Do not include:

- private client data;
- confidential commercial information;
- credentials, tokens, environment variables, or production secrets;
- organization-specific ground truth that is not intended for public reuse;
- private deployment details.

Use `EXP-000-ground-truth-template.md` or a sanitized example when a replay test needs hidden ground truth. Real organization-specific ground truth belongs outside the public repository.

## Security

Experiments that expand file, shell, network, API, or tool permissions require explicit human review. External content is always treated as untrusted data, not instructions.

See `../SECURITY.md` and `../AGENTS.md`.
