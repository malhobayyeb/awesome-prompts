# Awesome Prompts

![License: Public Domain](https://img.shields.io/badge/license-Unlicense-blue.svg)
![Status](https://img.shields.io/badge/status-active-success.svg)
![PRs](https://img.shields.io/badge/PRs-welcome-blue.svg)

> Modular prompt workflows for engineering tasks—repeatable, scope-bound, and ready for AI or human agents.

## Table of Contents
- [Why This Exists](#why-this-exists)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Why This Exists
Teams need prompts that are specific, deterministic, and safe to run in real repos. This library packages common workflows (testing, requirements, static analysis, architecture) into numbered playbooks with explicit scopes and outputs.

## Features
- Scope-bound workflows with explicit read/write rules per step.  
- Coverage of testing, requirements reverse-engineering, static analysis, and architecture review.  
- Deterministic, repeatable prompts suitable for AI or human operators.  
- Early non-functional requirements capture baked into the flow.  
- No runtime dependencies—everything is Markdown.

## Getting Started
1. Pick the prompt pack that matches your task.  
2. Follow the numbered steps in order.  
3. Respect each step’s **Scope** to avoid unintended changes.  
4. Save outputs to the specified doc paths to keep work auditable.

## Usage
- Testing: `TESTING.md` — map suites, log uncovered scenarios, and close gaps.  
- Requirements: `REQUIREMENTS.md` — reverse-engineer code/tests into agile requirements with NFRs.  
- Static analysis: `STATIC_ANALYSIS.md` — inventory tools, baseline findings, plan and remediate.  
- Architecture: `ARCHITECTURE.md` — map flows/dependencies, capture risks, and enforce boundaries.  
- Standards: `AGENTS.md` — formatting and prompt-engineering rules for this repo.

## Project Structure
```
AGENTS.md            # Prompt structure and engineering standards
ARCHITECTURE.md      # Architecture workflow
LICENSE              # Public domain dedication
README.md            # Project overview (this file)
REQUIREMENTS.md      # Requirements reverse-engineering workflow
STATIC_ANALYSIS.md   # Static analysis workflow
TESTING.md           # Testing and coverage workflow
```

## Contributing
- Follow the formatting and prompt rules in `AGENTS.md`.  
- Keep prompts actionable, explicit, and deterministic.  
- Submit small, focused PRs; avoid adding dependencies or non-prompt artifacts.

## License
Public domain dedication for prompt content (see `LICENSE`). Use, adapt, and redistribute freely.
