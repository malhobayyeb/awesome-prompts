# KMP Prompt Pack

This folder houses the Kotlin Multiplatform testing prompt workflow described in the main guide. Use it whenever you need to audit shared and platform-specific test coverage quickly.

## Quick links

- [Prompt script](./prompts.md) – step-by-step checklist for scanning tests, cross-checking source, and implementing missing coverage.
- [Repository overview](../README.md) – explains how this prompt pack fits with the Laravel and requirements flows.

## Workflow outputs

- Capture uncovered scenarios in `docs/tests/uncovered.md` (create the file in your target project if it does not exist).
- Update the relevant `*/tests` directories inside the project under audit as you work through the prompts.
