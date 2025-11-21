# Clean Architecture Prompt Pack

## Prompts

### Clean Architecture Refactor & Delivery

✅ Prompt 1

```md
Refactor the project to enforce Clean Architecture across Domain, Application, Infrastructure, and Interface layers. Keep all workflows and business logic unchanged while introducing repository abstractions, dependency inversion, and dependency injection. Avoid new libraries or frameworks and preserve readability, testability, and system behavior. Reply only with "Done" when finished—do not include any extra commentary.
Scope: Operate across the full codebase; restructure architecture without altering functional behavior or adding dependencies.
```

✅ Prompt 2

```md
Commit the completed refactor with a clear, descriptive message and push to the current remote branch. Do not switch branches during this process.
Scope: Version-control actions only; no additional code changes.
```

### System Comprehension Sequence

✅ Prompt 3

```md
Carefully read and internalize the entire source to build a high-level mental model of structure, objectives, and key components without making conclusions yet.
Scope: Read-only across the repository; do not modify files.
```

✅ Prompt 4

```md
Identify and isolate the modules, functions, or classes that form the backbone of core business logic. Reflect on their responsibilities, inputs/outputs, and integration points.
Scope: Read-only across the repository; make no edits.
```

✅ Prompt 5

```md
Map how components interact, including data flow, control logic, and architectural patterns. Highlight centralized or tightly coupled areas.
Scope: Read-only across the repository; do not modify files.
```

✅ Prompt 6

```md
Identify third-party libraries, frameworks, APIs, and external services. Note their roles, impact, and coupling.
Scope: Read-only across the repository; no modifications.
```

✅ Prompt 7

```md
Synthesize findings to surface subtle complexities, edge cases, and brittle areas. Evaluate scalability, maintainability, testability, and technical debt; flag refactoring/documentation needs.
Scope: Read-only across the repository; do not change code.
```

✅ Prompt 8

```md
Summarize the system in a structured form for a senior developer, highlighting critical design decisions, strengths, weaknesses, and improvement opportunities.
Scope: Produce written output only; no code changes.
```

✅ Prompt 9

```md
Trace control flow across key modules, focusing on branching, loops, and exception handling. Assess consistency and robustness of error paths and edge-case handling.
Scope: Read-only across the repository; no modifications.
```

✅ Prompt 10

```md
Assess the presence, structure, and effectiveness of unit, integration, and end-to-end tests. Note coverage gaps and areas needing improved edge-case testing.
Scope: Read-only across tests and source; do not create or modify files.
```

✅ Prompt 11

```md
Project how the system behaves under high load, large data volumes, or shifting requirements. Identify likely bottlenecks or failure points.
Scope: Read-only across the repository; no changes.
```

✅ Prompt 12

```md
Draft an outline for onboarding: architecture overview, key modules, known pitfalls, and areas needing immediate attention.
Scope: Produce documentation only; leave code unchanged.
```

### Architecture and Code Quality Enforcement

✅ Prompt 13

```md
Assess each layer (presentation, business logic, data access, etc.) for adherence to intended patterns and standards. Identify architectural drift, boundary violations, and pattern inconsistencies to drive alignment.
Scope: Read-only assessment across the codebase; note findings without code edits.
```

✅ Prompt 14

```md
Find dead code, unused functions, redundant branches, obsolete modules, and duplicated logic. Remove or simplify these elements to improve clarity, maintainability, and performance.
Scope: Modify only the redundant/obsolete code paths while respecting existing behavior; do not add dependencies.
```

✅ Prompt 15

```md
Locate comments referencing removed, refactored, or relocated code. Remove outdated or misleading notes to keep documentation accurate and noise-free.
Scope: Edit comments only; preserve functional code paths.
```

### Testing Coverage Expansion

✅ Prompt 16

```md
Design a phased plan to reach 100% coverage using existing test frameworks. Order phases from low-effort/high-impact to more complex areas, include unit and UI targets, and cover edge cases, error handling, and user flows. Do not introduce new dependencies.
Scope: Planning only; follow current testing patterns, naming, and folder structures.
```

✅ Prompt 17

```md
Implement the specified phase of the testing plan using existing tools and conventions. Add unit/UI tests for core logic, edge cases, and failure scenarios; ensure new tests are stable and repeatable.
Scope: Modify only test files per the current architecture and patterns; avoid new dependencies.
```
