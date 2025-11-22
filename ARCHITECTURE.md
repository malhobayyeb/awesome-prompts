# Architecture Prompt Pack

## Workflow
Run steps 1️⃣–5️⃣ once to map the architecture; repeat 6️⃣–8️⃣ to enforce quality and coverage.

### 1️⃣ Inventory Architecture and Dependencies
> Survey the codebase to identify key modules, layers (domain, application, infrastructure, interface), and external dependencies (frameworks, APIs, services). Note configs, entry points, and integration seams.  
> **Scope:** Read-only across the repository; respect ignore settings; do not modify files.

### 2️⃣ Map Control and Data Flows
> Trace control flow and data flow across core modules, focusing on branching, error handling, and integration points. Highlight coupling hotspots and boundary crossings.  
> **Scope:** Read-only across the repository; respect ignore settings; do not modify files.

### 3️⃣ Capture Non-Functional and Scalability Signals
> Assess performance, reliability, security, scalability, and observability considerations present in the architecture. Identify bottlenecks, failure points, and operational dependencies.  
> **Scope:** Read-only across code and configs; respect ignore settings; do not modify files.

### 4️⃣ Summarize Architectural Findings
> Write `docs/architecture/summary.md` with critical design decisions, strengths, weaknesses, risks, and improvement opportunities. Keep it concise for senior engineers.  
> **Scope:** Only write to `docs/architecture/summary.md`; do not change code.

### 5️⃣ Draft Refactor Plan
> Create a phased plan in `docs/architecture/plan.md` to address architectural drift, boundary violations, dead code, and pattern inconsistencies. Use markdown checkboxes for trackable tasks.  
> **Scope:** Planning only; write to `docs/architecture/plan.md`; do not modify code.

### 6️⃣ Enforce Architectural Boundaries (Repeatable)
> Apply targeted refactors to align modules with intended layers and patterns, removing dead code and outdated comments while preserving behavior.  
> **Scope:** Modify only affected source files and related comments; avoid new dependencies; keep behavior unchanged.

### 7️⃣ Re-run Quality Gates (Repeatable)
> Run static analysis and relevant linters/formatters to ensure refactors respect quality standards. Update `docs/architecture/baseline.md` with commands, timestamp, and deltas, and mark status in `docs/architecture/plan.md`.  
> **Scope:** Execute tools; respect ignore settings; update `docs/architecture/baseline.md` and `docs/architecture/plan.md`; do not change configs beyond necessary fixes.

### 8️⃣ Expand Test Coverage for Architecture-Sensitive Areas (Repeatable)
> Add or update tests covering core flows, edge cases, and error handling affected by architectural changes. Keep to existing test patterns and avoid new dependencies.  
> **Scope:** Modify only test files; do not change production code beyond necessary refactors already applied.
