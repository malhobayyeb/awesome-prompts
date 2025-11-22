# Static Analysis Prompt Pack

## Workflow
Run steps 1️⃣–5️⃣ once to establish the baseline; repeat 6️⃣–7️⃣ until the remediation plan is complete.

### 1️⃣ Inventory Static Analysis Setup
> Identify all static analysis tools, linters, formatters, and type checkers configured in the project. Locate config files, ignore lists, and custom rules. Summarize tool versions and entry points.  
> **Scope:** Read-only across the repository; respect ignore settings; do not modify configs or code.

### 2️⃣ Establish Baseline Report
> Run the configured static analysis tools using the project’s checked-in settings to produce a current-state report. Persist results to `docs/static-analysis/baseline.md`, including commands, timestamp, and summarized findings.  
> **Scope:** Execute tools; respect ignore settings; write only to `docs/static-analysis/baseline.md`; do not change source or configs.

### 3️⃣ Classify Findings
> Categorize baseline findings by severity, area, and type (correctness, security, performance, style). Flag probable false positives separately. Record the categorized list in `docs/static-analysis/findings.md`.  
> **Scope:** Read reports and code as needed; respect ignore settings; write only to `docs/static-analysis/findings.md`.

### 4️⃣ Map Suppressions and Ignores
> Enumerate existing suppressions and ignores (inline comments, config excludes, directory-level ignores). Assess whether they are justified or masking real issues. Document the list and rationale in `docs/static-analysis/findings.md`.  
> **Scope:** Read-only for code/config; respect ignore settings; append notes to `docs/static-analysis/findings.md`.

### 5️⃣ Prioritize Remediation
> Create an ordered remediation plan grouped by severity and effort. List quick wins, high-risk fixes, and deferred items with owners or teams if applicable. Use markdown checkboxes in `docs/static-analysis/plan.md` for trackable tasks.  
> **Scope:** Planning only; write to `docs/static-analysis/plan.md`; do not modify code or configs.

### 6️⃣ Implement First Remediation Batch (Repeatable)
> Apply fixes for the top-priority or quick-win items from `docs/static-analysis/plan.md`, keeping changes minimal and behavior-preserving. Remove unnecessary suppressions tied to the fixed issues.  
> **Scope:** Modify only affected source/test files and related suppressions; avoid dependency changes; keep behavior unchanged.

### 7️⃣ Re-run and Verify (Repeatable)
> Re-run the static analysis tools on the updated codebase. Update `docs/static-analysis/baseline.md` with the new run (commands, timestamp, deltas), and mark completed items in `docs/static-analysis/plan.md`.  
> **Scope:** Execute tools; respect ignore settings; update `docs/static-analysis/baseline.md` and `docs/static-analysis/plan.md`; no other file changes.
