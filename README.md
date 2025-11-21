# Awesome Prompts

![Status](https://img.shields.io/badge/status-active-success?style=flat-square)
![Maintained](https://img.shields.io/badge/maintained-yes-brightgreen?style=flat-square)
![PRs](https://img.shields.io/badge/PRs-welcome-blue?style=flat-square)
![Issues](https://img.shields.io/github/issues/mohammadalhobayyeb/awesome-prompts?style=flat-square)
![Stars](https://img.shields.io/github/stars/mohammadalhobayyeb/awesome-prompts?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/mohammadalhobayyeb/awesome-prompts?style=flat-square)
![License](https://img.shields.io/badge/license-TBD-lightgrey?style=flat-square)
![Docs Coverage](https://img.shields.io/badge/docs-100%25-blueviolet?style=flat-square)
![Made with Markdown](https://img.shields.io/badge/made%20with-Markdown-1f425f.svg)

> A curated collection of prompt playbooks that guide AI agents through rigorous testing and requirements-discovery workflows for Kotlin Multiplatform (KMP), Laravel, and documentation-first projects.

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
- **Bridge QA and requirements** – The `requirements` playbook extends beyond tests to produce actionable epics and user stories.

## Repository map

| Path | Description |
| --- | --- |
| `kmp/prompts.md` | Gap analysis + remediation workflow for Kotlin Multiplatform projects (shared + platform tests). |
| `laravel/prompts.md` | Laravel-centric checklist covering test scans, source parity checks, uncovered tracking, and implementation. |
| `requirements/prompts.md` | Documentation-first routine that derives agile requirements, fills gaps, tags coverage, and summarizes for stakeholders. |
| `.gitignore` | Keeps IDE, build, vendor, and environment clutter out of version control. |
| `README.md` | You are here—high-level guidance, badges, and usage tips. |

## Workflow deep dive

### KMP Playbook Highlights

1. **Test surface scan** – Inspect `commonTest`, `androidTest`, `iosTest`, etc., to understand coverage breadth.
2. **Source cross-check** – Align each major logic path or state machine with existing tests to detect gaps.
3. **Gap log** – Write actionable TODOs to `docs/tests/uncovered.md` in markdown task format.
4. **Validation loop** – Confirm items, prune false positives, and leave only real coverage needs.
5. **Targeted implementation** – Implement the first unchecked test-only scenario and mark it complete.

### Laravel Playbook Highlights

1. **`tests/` recon** – Map feature/HTTP/unit buckets, naming conventions, and helper traits.
2. **Business logic comparison** – Read application code (excluding Nova) to spot missing cases.
3. **`tests/uncovered.md` tracker** – Document uncovered cases as checkboxes for future sprints.
4. **Verification + cleanup** – Cross-check items with existing coverage and remove duplicates.
5. **Incremental delivery** – Implement the first outstanding item, run targeted tests, and mark it done.

### Requirements Playbook Highlights

1. **Behavior mining** – Infer functional requirements from existing tests.
2. **Source comprehension** – Validate behaviors against real code paths.
3. **Agile drafting** – Build `docs/tests/agile-requirements.md` with epics and user stories.
4. **Gap enrichment** – Add missing stories, tag coverage/implementation status, and note orphaned code.
5. **Polish & communicate** – Refine wording, order, metadata, and produce stakeholder summaries.

## Using the prompts

```bash
# 1. Pick your target domain
cd kmp   # or laravel / requirements

# 2. Open the optimized prompt list
bat prompts.md

# 3. Follow each prompt in order
#    - Respect the scope/writing restrictions
#    - Update docs/tests artifacts only where allowed

# 4. Commit findings or regenerated docs
git add docs/tests && git commit -m "Document uncovered KMP flows"
```

Tips:

- Stick to the scope for each prompt (many explicitly forbid editing anything outside a directory).
- Use lightweight viewers (e.g., `bat`, `less`, IDE preview) to keep context visible while working.
- When implementing missing tests, run *only* the targeted subset as explicitly required.

## Customization ideas

- **Add language tracks** – Drop in `flutter/`, `rails/`, or other stacks following the same `prompts.md` contract.
- **Parameterize scopes** – Use templating (e.g., `{{test_dir}}`) if you plan to auto-generate prompts per project.
- **Badge automation** – Hook up GitHub Actions to auto-update status badges (tests, lint, docs) referenced above.
- **Docs sync** – Point `docs/tests/*.md` to a knowledge base or wiki if you need richer collaboration.

## Contributing

1. Fork or branch from `main`.
2. Keep prompts deterministic—call out directories, scopes, and forbidden actions explicitly.
3. When adding a new playbook, update the [Repository map](#repository-map) and include any required doc targets.
4. Ensure prose stays concise; prefer checklists/numbered routines over paragraphs.
5. Submit a pull request describing the scenario your prompts cover and any assumptions.

_Need inspiration?_ Open an issue with the stack you’d like covered, and we can design a prompt set together.

## Roadmap

- [ ] Expand coverage beyond KMP/Laravel (e.g., React Native, Next.js).
- [ ] Provide sample `docs/tests/uncovered.md` and `agile-requirements.md` templates.
- [ ] Add automation scripts that feed prompts directly to AI agents.
- [ ] Publish a website showcasing each workflow with collapsible sections.

## Acknowledgements

- Thanks to every engineer who refined these routines through real QA war stories.
- Badges powered by [shields.io](https://shields.io/).
- Markdown previews tested with VS Code + JetBrains IDEs.

---

_Have ideas for more prompts or badges? Open an issue or start a discussion!_
