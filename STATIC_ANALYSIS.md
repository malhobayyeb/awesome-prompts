# Static Analysis Prompt Pack

## Workflow

### ✅ Inventory Static Analysis Setup
> Identify all static analysis tools, linters, formatters, and type checkers configured in the project. Locate config files, ignore lists, and custom rules. Summarize tool versions and entry points.  
> **Scope:** Read-only across the repository; do not modify configs or code.

### ✅ Establish Baseline Report
> Run the configured static analysis tools with default settings to produce a current-state report. Persist results to `docs/static-analysis/baseline.md`, including command(s) used, timestamp, and summarized findings.  
> **Scope:** Execute tools; write only to `docs/static-analysis/baseline.md`; do not change source or configs.

### ✅ Classify Findings
> Review the baseline report and categorize findings by severity, area, and type (correctness, security, performance, style). Flag probable false positives separately. Record the categorized list in `docs/static-analysis/findings.md`.  
> **Scope:** Read reports and code as needed; write only to `docs/static-analysis/findings.md`.

### ✅ Map Suppressions and Ignores
> Enumerate existing suppressions/ignores (inline comments, config excludes, directory-level ignores). Assess whether they are justified or masking real issues. Document the list and rationale in `docs/static-analysis/findings.md`.  
> **Scope:** Read-only for code/config; append notes to `docs/static-analysis/findings.md`.

### ✅ Prioritize Remediation
> Create an ordered remediation plan grouped by severity and effort. List quick wins, high-risk fixes, and deferred items with owners or teams if applicable. Use markdown checkboxes in `docs/static-analysis/plan.md` for trackable tasks.  
> **Scope:** Planning only; write to `docs/static-analysis/plan.md`; do not modify code or configs.

### ✅ Implement First Remediation Batch
> Apply fixes for the top-priority/quick-win items from `docs/static-analysis/plan.md`, keeping changes minimal and behavior-preserving. Remove unnecessary suppressions tied to the fixed issues.  
> **Scope:** Modify only affected source/test files and related suppressions; avoid dependency changes.

### ✅ Re-run and Verify
> Re-run the static analysis tools on the updated codebase. Update `docs/static-analysis/baseline.md` with the new run (commands, timestamp, deltas), and mark completed items in `docs/static-analysis/plan.md`.  
> **Scope:** Execute tools; update `docs/static-analysis/baseline.md` and `docs/static-analysis/plan.md`; no other file changes.

