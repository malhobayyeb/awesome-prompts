# Testing & QA Prompt Pack

## Workflow
Run steps 1️⃣–5️⃣ once to map and validate gaps; repeat 6️⃣ until every item in `docs/tests/uncovered.md` is checked.

### 1️⃣ Map All Test Suites
> Scan every available test suite (unit, integration, end-to-end, UI) to map structure, themes, conventions, and coverage focus.  
> **Scope:** Read-only access to all test directories; respect ignore settings; make no file changes.

### 2️⃣ Cross-Reference Tests with Source
> Compare existing tests to source modules to identify uncovered logic branches, state machines, user flows, and edge cases. Capture missing coverage candidates.  
> **Scope:** Read-only access to all test directories and source code; respect ignore settings; do not modify files.

### 3️⃣ Log Uncovered Scenarios
> Write a precise checklist of uncovered logic paths, business rules, and edge cases to `docs/tests/uncovered.md` using markdown checkboxes (- [ ]). Make each item specific and actionable.  
> **Scope:** Only write to `docs/tests/uncovered.md`; do not create or edit any other files.

### 4️⃣ Assess Test Suite Effectiveness
> Evaluate the presence, structure, and effectiveness of unit, integration, and end-to-end tests. Add any uncovered edge cases, error paths, and failure handling gaps as new checklist items in `docs/tests/uncovered.md`.  
> **Scope:** Read tests and source; append findings only to `docs/tests/uncovered.md`; do not modify other files.

### 5️⃣ Validate Uncovered Log
> Read `docs/tests/uncovered.md`, cross-check each entry against existing tests, and remove items already fully covered so only real gaps remain.  
> **Scope:** Only modify `docs/tests/uncovered.md`; no other file changes.

### 6️⃣ Implement First Gap (Repeatable)
> Open `docs/tests/uncovered.md`, pick the first unchecked item, implement targeted test(s) to cover it, and mark the item as checked (- [x]) once verified. Avoid touching production code.  
> **Scope:** Modify only test directories and `docs/tests/uncovered.md`; do not change source files or other docs.

# Test Architecture & Patterns Prompt Pack

## Workflow
Run steps 1️⃣–3️⃣ once to codify guardrails and backlog inside `docs/tests/architecture.md`; repeat 4️⃣–6️⃣ for each backlog item until every checkbox in that file is complete.

### 1️⃣ Audit Test Architecture
> Scan all test directories (unit, integration, e2e, UI, contract) to map folder layout, fixture layering, helper modules, mocking boundaries, data builders, and naming conventions. Flag spots where suites deviate from deterministic, isolated, and DRY best practices.  
> **Scope:** Read-only access to all test directories and shared test utilities; do not modify files.

### 2️⃣ Define Guardrails in One Doc
> Create `docs/tests/architecture.md` (or update it if present) with sections for approved suite structure, naming rules, fixture lifecycles, reusable helpers, and mocking strategy. Use markdown checklists for every non-negotiable pattern so actionable items live in this single file.  
> **Scope:** Modify only `docs/tests/architecture.md`; no other files.

### 3️⃣ Log DRY Gaps & Backlog Items
> In the same file, append a "Refactor Backlog" section where each duplicated setup, fixture drift, or brittle pattern becomes a checkbox entry with file paths, desired outcome, and linked guardrail requirement. Keep all actionable items in `docs/tests/architecture.md`.  
> **Scope:** Update only `docs/tests/architecture.md`; leave other files untouched.

### 4️⃣ Implement First Backlog Entry (Repeatable)
> Open `docs/tests/architecture.md`, grab the first unchecked backlog item, and refactor the referenced tests to reuse shared helpers, align naming, or restructure folders according to the guardrails. Do not modify production code or non-test docs.  
> **Scope:** Edit only the affected test directories and shared test utilities referenced by the backlog item; no application source changes.

### 5️⃣ Mark Progress in the Same Doc
> After refactoring, return to `docs/tests/architecture.md`, mark the backlog item as checked (- [x]), and jot a short note on what changed and which suites were touched so the file stays the single source of truth.  
> **Scope:** Update only `docs/tests/architecture.md`; no other doc edits.

### 6️⃣ Verify Against Guardrails
> Run the impacted test suites, confirm the new structure honors every guardrail, and, if guardrails evolved, update the relevant checklist entries in `docs/tests/architecture.md` to reflect the latest patterns.  
> **Scope:** Read/execute tests as needed; modify only `docs/tests/architecture.md` when documenting verification.
