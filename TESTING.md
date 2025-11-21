# Testing & QA Prompt Pack

## Universal Testing Workflows

### ✅ Map All Test Suites
> Scan every available test suite (unit, integration, end-to-end, UI) to map structure, themes, conventions, and coverage focus.  
> **Scope:** Read-only access to all test directories; respect ignore settings; make no file changes.

### ✅ Cross-Reference Tests with Source
> Compare existing tests to source modules to identify uncovered logic branches, state machines, user flows, and edge cases. Capture missing coverage candidates.  
> **Scope:** Read-only access to all test directories and source code; respect ignore settings; do not modify files.

### ✅ Log Uncovered Scenarios
> Write a precise checklist of uncovered logic paths, business rules, and edge cases to `docs/tests/uncovered.md` using markdown checkboxes (- [ ]). Make each item specific and actionable.  
> **Scope:** Only write to `docs/tests/uncovered.md`; do not create or edit any other files.

### ✅ Validate Uncovered Log
> Read `docs/tests/uncovered.md`, cross-check each entry against existing tests, and remove items already fully covered so only real gaps remain.  
> **Scope:** Only modify `docs/tests/uncovered.md`; no other file changes.

### ✅ Implement First Gap
> Open `docs/tests/uncovered.md`, pick the first unchecked item, implement targeted test(s) to cover it, and mark the item as checked (- [x]) once verified. Avoid touching production code.  
> **Scope:** Modify only test directories and `docs/tests/uncovered.md`; do not change source files or other docs.

### ✅ Assess Test Suite Effectiveness
> Evaluate the presence, structure, and effectiveness of unit, integration, and end-to-end tests. Highlight edge cases, error paths, and failure handling lacking coverage; report findings in this output only.  
> **Scope:** Read-only across tests and source code; do not create or modify any files.

### ✅ Coverage Expansion Plan
> Design a phased plan to increase coverage using existing testing frameworks and patterns. Order phases from low-effort/high-impact to more complex areas, covering unit, integration, UI, edge, and failure cases.  
> **Scope:** Planning only; produce the plan in this output; do not edit the repository.

### ✅ Implement Coverage Plan Phase
> Implement the current phase of the coverage plan by adding stable, repeatable tests for core logic, edge cases, and failure scenarios using established conventions. If running tests, limit execution to the affected subset.  
> **Scope:** Modify only test files per existing architecture and conventions; avoid new dependencies and production code changes.
