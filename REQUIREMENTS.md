# Requirements Prompt Pack

## Workflow
Run steps 1️⃣–7️⃣ once to build the baseline requirements; repeat 8️⃣ to maintain and refine updates as the system evolves.

### 1️⃣ Map Behaviors From Tests
> Analyze all test files (unit, integration, feature, system) to infer validated behaviors, business rules, user interactions, and system flows. Capture high-level functional requirements implied by the tests.  
> **Scope:** Read-only access to all test directories; respect ignore settings; do not modify tests.

### 2️⃣ Analyze Source for Implemented Features
> Explore source modules to understand implemented features, domain logic, UI/UX flows, validation, and service interactions. Document notable behaviors and constraints.  
> **Scope:** Read-only access to source code; respect ignore settings; do not create or modify files.

### 3️⃣ Draft Agile Requirements Doc
> Create `docs/tests/agile-requirements.md` with Epics and grouped user stories formatted as "As a [role], I want to [action] so that [outcome]." Base content on findings from tests and source.  
> **Scope:** Only write to `docs/tests/agile-requirements.md`; do not change other files.

### 4️⃣ Surface Missing or Implicit Requirements
> Compare the drafted requirements against observed functionality to find behaviors or logic paths not yet documented. Add these gaps to `docs/tests/agile-requirements.md` as new epics or stories.  
> **Scope:** Read code and tests; append only to `docs/tests/agile-requirements.md`; do not edit other files.

### 5️⃣ Expand Requirements for Gaps
> For each uncovered behavior, author precise user stories (and epics if needed) and append them under the appropriate sections in `docs/tests/agile-requirements.md`, ensuring no redundancy.  
> **Scope:** Only modify `docs/tests/agile-requirements.md`; no other files.

### 6️⃣ Tag Coverage Status
> For every user story in `docs/tests/agile-requirements.md`, determine implementation and test coverage status (e.g., ✅ implemented, 🧪 tested, ❌ missing) and annotate accordingly.  
> **Scope:** Read-only access to code and tests; only update `docs/tests/agile-requirements.md`.

### 7️⃣ Detect Orphaned Functionality
> Identify source or test code not represented by any epic or story and log it in `docs/tests/agile-requirements.md` with recommendations (remove, document, or integrate).  
> **Scope:** Read code and tests; only write to `docs/tests/agile-requirements.md`; do not modify code or tests.

### 8️⃣ Refine and Normalize Requirements
> Review `docs/tests/agile-requirements.md` to merge duplicates, clarify vague language, enforce consistent formatting, and reorder for logical flow so each epic is cohesive.  
> **Scope:** Only edit `docs/tests/agile-requirements.md`; no other files.
