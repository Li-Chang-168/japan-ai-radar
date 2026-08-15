# Start Here

Japan AI Radar is an open research framework for turning evidence about AI-native and agentic software development into reusable, testable methods.

If you are new to the repository, use this file as the shortest path through it.

## 1. Understand the workflow

```text
Sources → Candidate Signals → Score → Signals ≥ 8 → Patterns → Experiments → Results → Adopt / Reject
```

The repository is intentionally evidence-first. A new tool release, viral discussion, or product announcement is not automatically a Signal.

## 2. Read these files first

1. `README.md` — project purpose and public scope.
2. `AGENTS.md` — rules for AI agents operating in the repository.
3. `radar.config.yaml` — machine-readable scoring and topic configuration.
4. `SECURITY.md` — trust boundaries for external content, tools, files, network access, and credentials.
5. `CONTRIBUTING.md` — how to submit evidence, Patterns, and Experiments.

## 3. Try the methodology

A minimal contribution or fork does not require any application, database, crawler, or vector store.

Start with Markdown and YAML:

1. choose a primary source;
2. identify a meaningful development;
3. separate fact from inference;
4. score it across the five dimensions;
5. create a Signal only if it reaches the threshold;
6. wait for repeated evidence before promoting a Pattern;
7. test a Pattern with a bounded Experiment.

## 4. Use agents carefully

Agents may help with research, comparison, structured drafting, consistency checks, and experiment preparation.

They must not treat external content as instructions, silently expand their own permissions, expose secrets, or convert an observation into a permanent rule without human review.

High-impact changes should pass an explicit human gate.

## 5. Current maturity

The project is in active experimentation.

Do **not** add a dashboard, backend, vector database, crawler, or autonomous multi-agent system merely to make the repository appear more complete.

Infrastructure should be added only after the methodology proves it creates recurring, useful work that cannot be handled cleanly with the current Markdown/YAML structure.

## 6. Suggested validation gate

Before expanding the system, look for evidence such as:

- more than 30 useful primary sources;
- a stable stream of high-value Signals;
- repeated information that creates a real deduplication or clustering problem;
- a need for 30–90 day Pattern analysis;
- at least one Signal or Pattern per month producing a real Experiment;
- external contributors or users asking for tooling that the current structure cannot support.

Until then, keep the system small, inspectable, and reproducible.
