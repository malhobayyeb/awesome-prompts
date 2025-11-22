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
Run steps 1️⃣–4️⃣ once to capture only confirmed drifts inside `docs/tests/drifts.md`; repeat 5️⃣ until the checklist is empty.

### 1️⃣ Audit Established Architecture
> Read existing architecture guardrails and the current test suites (unit, integration, e2e, UI, contract) to understand the approved patterns, principles, practices, and standards before spotting issues.  
> **Scope:** Read-only access to guardrail docs and all test directories; do not modify files.

### 2️⃣ Detect Architecture Drifts
> Compare the established standards from step 1 against the live tests to locate every deviation (duplicated setups, fixture misuse, naming drift, brittle helpers, etc.). Capture supporting evidence and affected paths.  
> **Scope:** Read-only access to test directories and shared test utilities.

### 3️⃣ Log Drifts as Actionable Items
> Record each drift in `docs/tests/drifts.md` as an unchecked checklist entry (- [ ]) that describes the issue, target files, and desired corrective action. Keep all actionable backlog items in this single file.  
> **Scope:** Modify only `docs/tests/drifts.md`; do not edit other files.

### 4️⃣ Validate Real Drifts
> Re-read `docs/tests/drifts.md` and confirm each entry is a true deviation. Remove any false positives so the checklist reflects only real drifts ready for implementation.  
> **Scope:** Update only `docs/tests/drifts.md`; no other file changes.

### 5️⃣ Implement First Drift (Repeatable)
> Take the first unchecked drift from `docs/tests/drifts.md`, refactor the referenced tests to eliminate the issue, run the relevant suites, then mark the checklist item as checked (- [x]) with a short verification note. Avoid touching production (non-test) code.  
> **Scope:** Modify only the affected test directories, shared test utilities, and `docs/tests/drifts.md`; keep application source files untouched.
