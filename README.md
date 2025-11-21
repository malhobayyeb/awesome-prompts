# Awesome Prompts

![Status](https://img.shields.io/badge/status-active-success?style=flat-square)
![Maintained](https://img.shields.io/badge/maintained-yes-brightgreen?style=flat-square)
![PRs](https://img.shields.io/badge/PRs-welcome-blue?style=flat-square)
![Issues](https://img.shields.io/github/issues/mohammadalhobayyeb/awesome-prompts?style=flat-square)
![Stars](https://img.shields.io/github/stars/mohammadalhobayyeb/awesome-prompts?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/mohammadalhobayyeb/awesome-prompts?style=flat-square)
![License](https://img.shields.io/badge/license-Unlicense-lightgrey?style=flat-square)
![Docs Coverage](https://img.shields.io/badge/docs-100%25-blueviolet?style=flat-square)
![Made with Markdown](https://img.shields.io/badge/made%20with-Markdown-1f425f.svg)

> A curated collection of prompt playbooks that guide AI agents through testing, static analysis, architectural alignment, and requirements discovery across any stack.

## Table of Contents

1. [Why this repository exists](#why-this-repository-exists)
2. [Repository map](#repository-map)
3. [Workflow deep dive](#workflow-deep-dive)
4. [Using the prompts](#using-the-prompts)
5. [Customization ideas](#customization-ideas)
6. [Contributing](#contributing)
7. [Roadmap](#roadmap)
8. [Acknowledgements](#acknowledgements)

## Why this repository exists

- **Codify testing intuition** – Each prompt sequence captures a proven exploratory or gap-closing routine so teams can reuse it or hand it to AI agents.
- **Keep audits reproducible** – Scopes, directories, and guardrails are spelled out, so repeated runs stay consistent across contributors.
- **Accelerate onboarding** – New engineers can understand how to inspect a codebase without wading through sprawling docs.
- **Bridge QA, architecture, and requirements** – Playbooks span testing, static analysis, architectural alignment, and epics/user stories for full lifecycle coverage.

## Repository map

| Path | Description |
| --- | --- |
| `AGENTS.md` | Prompt format and engineering standards (scope, tone, repeatability) that every pack follows. |
| `TESTING.md` | Universal testing and QA workflows for mapping suites, logging gaps, and implementing coverage. |
| `ARCHITECTURE.md` | Clean architecture refactor guidance plus system comprehension and coverage assessment prompts. |
| `REQUIREMENTS.md` | Documentation-first routine that derives agile requirements, fills gaps, tags coverage, and summarizes for stakeholders. |
| `STATIC_ANALYSIS.md` | Static analysis workflows for inventory, baseline reporting, triage, and remediation. |
| `.gitignore` | Keeps IDE, build, vendor, and environment clutter out of version control. |
| `README.md` | You are here—high-level guidance, badges, and usage tips. |

## Workflow deep dive

### Testing & QA Highlights

1. **Test suite survey** – Map unit, integration, end-to-end, and UI suites for structure and themes.
2. **Source cross-check** – Align code paths and behaviors against existing tests to spot gaps.
3. **Gap log** – Record uncovered cases in `docs/tests/uncovered.md` with actionable checkboxes.
4. **Validation loop** – Reconcile the log with current tests and prune any false positives.
5. **Targeted implementation** – Implement and verify the first unchecked gap, then mark it complete.

### Static Analysis Highlights

1. **Tool inventory** – Locate linters, formatters, type checkers, configs, and ignores.
2. **Baseline run** – Execute tools and capture results in `docs/static-analysis/baseline.md`.
3. **Finding triage** – Classify issues, note false positives, and log suppressions in `docs/static-analysis/findings.md`.
4. **Plan remediation** – Build a checkbox plan in `docs/static-analysis/plan.md`, then knock out quick wins.
5. **Re-run verification** – Re-execute tools, update reports, and mark completed items.

### Architecture Playbook Highlights

1. **Clean architecture refactor** – Enforce layer boundaries, inversion, and repository abstractions without altering behavior or adding dependencies.
2. **Version control action** – Commit the refactor with a descriptive message on the current branch.
3. **System comprehension** – Read and model structure, logic flows, coupling points, and external dependencies.
4. **Coverage and robustness review** – Assess tests, data flow, control paths, and error handling; surface brittle areas.

### Requirements Playbook Highlights

1. **Behavior mining** – Infer functional requirements from existing tests.
2. **Source comprehension** – Validate behaviors against real code paths.
3. **Agile drafting** – Build `docs/tests/agile-requirements.md` with epics and user stories.
4. **Gap enrichment** – Add missing stories, tag coverage/implementation status, and note orphaned code.
5. **Polish & communicate** – Refine wording, order, metadata, and produce stakeholder summaries.

## Using the prompts

```bash
# 1. Pick your target domain
open TESTING.md   # or ARCHITECTURE.md / REQUIREMENTS.md / STATIC_ANALYSIS.md

# 2. Open the optimized prompt list
bat TESTING.md    # swap in the file you’re using

# 3. Follow each prompt in order
#    - Respect the scope/writing restrictions
#    - Write only to the allowed doc paths for that pack

# 4. Commit findings or regenerated docs
git add docs && git commit -m "Document findings from static analysis run"
```

Tips:

- Stick to the scope for each prompt (many explicitly forbid editing anything outside a directory).
- Use lightweight viewers (e.g., `bat`, `less`, IDE preview) to keep context visible while working.
- When implementing changes (tests or fixes), run only the targeted subset specified by the prompt.
- If you create new prompts, mirror the format and scope discipline defined in `AGENTS.md`.

## Customization ideas

- **Add domain packs** – Introduce new files (e.g., `FRONTEND.md`, `DATA.md`) using the same prompt layout and scope rules.
- **Parameterize scopes** – Use templating (e.g., `{{tests_dir}}`, `{{lint_cmd}}`) for organizations that auto-generate project-specific packs.
- **Badge automation** – Hook up CI to refresh badges for lint/test/docs status referenced here.
- **Docs sync** – Point `docs/tests/*` and `docs/static-analysis/*` to your knowledge base if you need richer collaboration.

## Contributing

1. Fork or branch from `main`.
2. Keep prompts deterministic—call out directories, scopes, and forbidden actions explicitly.
3. When adding a new playbook, update the [Repository map](#repository-map) and include any required doc targets.
4. Ensure prose stays concise; prefer checklists/numbered routines over paragraphs.
5. Submit a pull request describing the scenario your prompts cover and any assumptions.

_Need inspiration?_ Open an issue with the stack you’d like covered, and we can design a prompt set together.

## Roadmap

- [ ] Provide sample templates for `docs/tests/uncovered.md`, `docs/tests/agile-requirements.md`, and `docs/static-analysis/*.md`.
- [ ] Add more domain packs (e.g., frontend frameworks, data pipelines, mobile).
- [ ] Add automation scripts that feed prompts directly to AI agents or CI pipelines.
- [ ] Publish a website showcasing each workflow with collapsible sections and copy-friendly snippets.

## Acknowledgements

- Thanks to every engineer who refined these routines through real QA war stories.
- Badges powered by [shields.io](https://shields.io/).
- Markdown previews tested with VS Code + JetBrains IDEs.

---

_Have ideas for more prompts or badges? Open an issue or start a discussion!_
