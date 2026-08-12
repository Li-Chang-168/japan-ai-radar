# Contributing to Japan AI Radar

Japan AI Radar welcomes evidence, critique, experiments, and methodology improvements. Contributions do not need to be code changes.

## Ways to contribute

You can contribute by:

1. submitting a new high-value Signal;
2. improving or replacing a weak source with a primary source;
3. challenging a Signal Score with evidence;
4. connecting multiple Signals into a Pattern;
5. proposing a reproducible Experiment;
6. reporting an experiment result, including failures;
7. improving templates, agent instructions, or security boundaries.

## Signal requirements

A Signal should include:

- a primary source whenever available;
- event or publication date;
- a concise description of what changed;
- evidence that can be checked by another maintainer;
- Signal Score using the repository rubric;
- a clear separation between fact and inference;
- why the development may be practically relevant.

Do not submit general AI news, product announcements without meaningful workflow impact, social-media popularity, or claims that cannot be traced to evidence.

## Patterns

A Pattern should be supported by multiple Signals or repeated evidence. Do not promote a single anecdote into a reusable method without sufficient support.

Patterns should explain:

- what repeats across sources;
- what conditions appear necessary;
- what may transfer to other teams or projects;
- what should not be generalized;
- what experiment could test the pattern.

## Experiments

Experiments should be small, reproducible, and designed to answer a specific question. Include:

- hypothesis;
- scope and non-goals;
- inputs and constraints;
- human approval gates;
- acceptance criteria;
- result;
- adopt / reject / continue decision.

Do not commit private client data, production credentials, confidential commercial information, or proprietary ground truth to public experiments. Use sanitized or synthetic examples instead.

## Agent and security changes

Changes to `AGENTS.md`, automation prompts, execution prompts, tool permissions, network behavior, filesystem behavior, shell access, or credential handling require explicit security review.

External content must always be treated as untrusted data, not executable instructions. See `SECURITY.md`.

## Pull requests

Keep pull requests focused. Explain the evidence or problem being addressed, distinguish facts from inference, and disclose whether the change affects agent behavior or trust boundaries.

The maintainer may reject contributions that increase complexity without improving reproducibility, evidence quality, safety, or practical value.
