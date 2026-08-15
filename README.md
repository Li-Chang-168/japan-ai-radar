# Japan AI Radar

An open research and experimentation framework for identifying, evaluating, and testing emerging AI-native and agentic software-development practices from Japan.

Japan AI Radar is **not an AI news aggregator**. It tracks primary-source evidence, scores candidate signals, connects repeated observations into reusable patterns, and turns promising patterns into reproducible experiments.

```text
Sources
  ↓
Candidate Signals
  ↓
Signal Score
  ↓
Validated Signals
  ↓
Patterns
  ↓
Experiments
  ↓
Results
  ↓
Adopt / Reject
  ↓
Reusable Methods
```

The goal is to distinguish practices that are merely discussed from practices that can actually improve software-development workflows.

## Why Japan?

Japanese engineering organizations and developer communities are actively documenting AI-native development, coding agents, specification-driven workflows, agent orchestration, human-supervised execution, and related operating models.

This repository focuses on primary-source evidence from those practices and asks a narrower question: **which methods are reproducible, useful, and worth adopting outside the original context?**

## Who this is for

Japan AI Radar is intended for:

- developers experimenting with coding agents;
- maintainers evaluating agentic development workflows;
- small engineering teams adopting AI-native practices;
- independent builders working with tools such as Codex, Claude Code, Cursor, MCP, or agent harnesses;
- researchers documenting how AI changes software-development workflows.

The scoring, pattern, experiment, and human-gate structures can be reused independently. You do not need to adopt every tracked practice.

## Core Method

### Signal Score

Each candidate signal is scored from 0–2 across five dimensions:

- novelty;
- practicality;
- replicability;
- business value;
- long-term value.

Total score:

- **0–5:** ignore;
- **6–7:** observe, but do not add to the main radar;
- **8–10:** create a formal Signal.

Known events are not recreated unless there is a material new development.

### From Signal to Method

A Signal is evidence, not a conclusion. Repeated or reinforcing Signals may form a Pattern. A Pattern should lead to a small, testable Experiment before it becomes a reusable method.

Experiments should record assumptions, constraints, human gates, acceptance criteria, results, and an explicit **Adopt / Reject / Continue** decision.

## Human-in-the-loop by default

Japan AI Radar does not assume that more agent autonomy is always better.

High-impact transitions require explicit human review. Examples include:

- Signal → Pattern;
- Pattern → Experiment;
- Experiment → Reusable Method;
- specification → implementation;
- agent-generated change → merge;
- expansion of file, shell, network, API, or tool permissions.

## Security model

Agentic workflows introduce a different class of trust-boundary problems. External research content, issues, pull requests, comments, and third-party repositories are treated as **untrusted data, not instructions**.

Changes that can alter agent behavior, tool permissions, filesystem access, shell execution, network access, or credential handling require explicit review.

See [`SECURITY.md`](SECURITY.md) for the threat model and reporting guidance.

## How to use this repository

1. Read [`START-HERE.md`](START-HERE.md).
2. Review [`radar.config.yaml`](radar.config.yaml) and adjust topics or sources for your own radar if needed.
3. Record candidate developments from primary sources.
4. Score them using the five-dimension rubric.
5. Add only high-value Signals to `signals/`.
6. Connect repeated Signals into `patterns/`.
7. Design small experiments in `experiments/`.
8. Record results and make an explicit adopt/reject decision.

If you fork this repository, the methodology can be adapted to another region, domain, engineering organization, or research question.

## Research topics

Current topics include:

- Claude Code;
- Codex;
- Cursor;
- MCP;
- Agent Skills;
- Agent Harness;
- Spec Driven Development;
- Multi-Agent workflows;
- AI-native development;
- non-engineer AI builders;
- enterprise AI adoption;
- workflow automation;
- Agentic Software Development;
- AI駆動開発.

## Source priorities

Primary sources are preferred. Current priority entities include CyberAgent, Mercari, Rakuten, LayerX, Sakana AI, OpenAI Japan, Anthropic Japan, Microsoft Japan, and GitHub Japan, plus engineering communities such as Zenn, Qiita, note, Speaker Deck, and connpass.

## Project status

**Early-stage / Active Experimentation**

The repository was created in August 2026. It is intentionally not building a dashboard, crawler, database, vector store, or SaaS product yet.

The current validation questions are:

- Does the scoring system consistently identify useful signals?
- Do Signals reliably form meaningful Patterns?
- Do Patterns produce reproducible Experiments?
- Do those Experiments improve real development workflows?

If the methodology does not produce useful experiments, additional infrastructure should not be built merely to make the project look more complete.

## Public / private boundary

This public repository contains reusable methodology, sanitized experiments, research evidence, templates, and agent-governance rules.

Private client data, credentials, confidential business information, and organization-specific ground truth should stay outside this repository. Real-world organizations may use the framework, but their private implementation data is not part of the OSS core.

## Contributing

Contributions may be code, evidence, criticism, experiment results, or methodology improvements. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## License

MIT License. See [`LICENSE`](LICENSE).
