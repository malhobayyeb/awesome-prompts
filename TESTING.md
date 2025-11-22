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
Run steps 1️⃣–4️⃣ once to define architecture guardrails; repeat 5️⃣–6️⃣ until every refactor in `docs/tests/refactors.md` is complete.

### 1️⃣ Audit Test Architecture
> Scan all test directories (unit, integration, e2e, UI, contract) to map folder layout, fixture layering, helper modules, mocking boundaries, data builders, and naming conventions. Flag spots where suites deviate from deterministic, isolated, and DRY best practices.  
> **Scope:** Read-only access to all test directories and shared test utilities; do not modify files.

### 2️⃣ Define Architecture Guardrails
> Create or update `docs/tests/architecture.md` to document the approved suite structure, naming rules, fixture lifecycles, reusable helpers, mocking strategy, and dependency boundaries. Use markdown checklists for required patterns and annotate examples pulled from current suites.  
> **Scope:** Only modify `docs/tests/architecture.md`; no other file changes.

### 3️⃣ Log DRY & Pattern Gaps
> Compare existing suites against the guardrails and record every duplicated setup, fixture drift, or brittle pattern as precise checklist items in `docs/tests/refactors.md` (one per gap) with file references and desired outcomes.  
> **Scope:** Append findings only to `docs/tests/refactors.md`; leave other files untouched.

### 4️⃣ Prioritize Architecture Fixes
> Group backlog entries by suite, order them by risk vs effort, and note dependencies so DRY refactors land in a logical sequence. Ensure each item links back to the relevant guardrail requirement inside `docs/tests/refactors.md`.  
> **Scope:** Read tests and planning docs; update `docs/tests/refactors.md` only.

### 5️⃣ Implement First Pattern Refactor (Repeatable)
> Open `docs/tests/refactors.md`, grab the first unchecked item, and refactor the referenced tests to reuse shared helpers, align naming, or restructure folders according to the guardrails. Do not modify production code or non-test docs.  
> **Scope:** Edit only the affected test directories and shared test utilities referenced by the backlog item; no application source changes.

### 6️⃣ Verify & Close Architecture Item
> Run the impacted test suites, confirm the new structure meets guardrails, then mark the backlog entry as checked (- [x]) in `docs/tests/refactors.md`. Update `docs/tests/architecture.md` only if guardrails evolved during the refactor.  
> **Scope:** Update `docs/tests/refactors.md` (and `docs/tests/architecture.md` when needed); restrict code edits to the test files already touched in step 5.
