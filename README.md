# Awesome Prompts

![License: Public Domain](https://img.shields.io/badge/license-Unlicense-blue.svg)
![Status](https://img.shields.io/badge/status-active-success.svg)
![PRs](https://img.shields.io/badge/PRs-welcome-blue.svg)

> A modular library of prompt workflows for engineering tasks—repeatable, scope-bound, and ready for AI or human agents.

## Why This Exists
Engineering teams need prompts that are specific, deterministic, and safe to run in real repos. This collection packages common workflows (testing, requirements, static analysis, architecture) into clear, stepwise playbooks with explicit scopes.

## Prompt Packs
- `TESTING.md` — map test suites, log uncovered scenarios, and close coverage gaps.  
- `REQUIREMENTS.md` — reverse-engineer code/tests into agile requirements with early non-functional capture.  
- `STATIC_ANALYSIS.md` — inventory linters/tools, baseline findings, plan and execute remediations.  
- `ARCHITECTURE.md` — map flows and dependencies, capture risks, and enforce architectural quality.

## Getting Started
1. Open the relevant prompt pack and follow the numbered steps in order.  
2. Respect each step’s **Scope** (read/write boundaries and allowed files).  
3. Save outputs to the specified doc paths to keep results repeatable and auditable.

## Documentation
- Standards and formatting: `AGENTS.md`.  
- Testing workflow: `TESTING.md`.  
- Requirements reverse-engineering: `REQUIREMENTS.md`.  
- Static analysis: `STATIC_ANALYSIS.md`.  
- Architecture review: `ARCHITECTURE.md`.

## Contributing
- Follow the prompt-engineering rules in `AGENTS.md`.  
- Keep prompts actionable, explicit, and deterministic.  
- Submit focused PRs; avoid adding non-prompt artifacts or dependencies.

## License
Public domain dedication for prompt content (see `LICENSE`). Use, adapt, and redistribute freely.***
