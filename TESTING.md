# Testing & QA Prompt Pack

## Universal Testing Workflows
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
