# Static Analysis Prompt Pack

## Workflow
Run steps 1️⃣–4️⃣ once to inventory and log findings; repeat 5️⃣–6️⃣ to remediate and track progress.

### 1️⃣ Inventory Static Analysis Setup
> Identify all static analysis tools, linters, formatters, and type checkers configured in the project. Locate config files, ignore lists, and custom rules. Summarize tool versions and entry points.  
> **Scope:** Read-only across the repository; respect ignore settings; do not modify configs or code.

### 2️⃣ Run Static Analysis
> Execute the configured static analysis tools using the project’s checked-in settings.  
> **Scope:** Execute tools; respect ignore settings; do not change source or configs.

### 3️⃣ Log Results
> Record commands, timestamp, and summarized findings from the analysis run into `docs/static-analysis/findings.md`, using markdown checkboxes for actionable items.  
> **Scope:** Write only to `docs/static-analysis/findings.md`; do not modify source or configs.

### 4️⃣ Classify Findings
> Categorize findings by severity, area, and type (correctness, security, performance, style). Flag probable false positives separately. Record all actionable items as markdown checkboxes in `docs/static-analysis/findings.md`.  
> **Scope:** Read reports and code as needed; respect ignore settings; write only to `docs/static-analysis/findings.md`.

### 5️⃣ Map Suppressions and Ignores
> Enumerate existing suppressions and ignores (inline comments, config excludes, directory-level ignores). Assess whether they are justified or masking real issues. Add actionable items as markdown checkboxes to `docs/static-analysis/findings.md` with rationale.  
> **Scope:** Read-only for code/config; respect ignore settings; append notes to `docs/static-analysis/findings.md`.

### 6️⃣ Prioritize Remediation
> Create an ordered remediation list grouped by severity and effort. Keep all actionable items as markdown checkboxes in `docs/static-analysis/findings.md`, marking priority and ownership if applicable.  
> **Scope:** Planning only; write to `docs/static-analysis/findings.md`; do not modify code or configs.

### 7️⃣ Implement First Remediation Item (Repeatable)
> Open `docs/static-analysis/findings.md`, take the top unchecked item, apply the fix with minimal, behavior-preserving changes, remove any related suppressions, and mark the item as checked when verified.  
> **Scope:** Modify only affected source/test files and related suppressions; avoid dependency changes; keep behavior unchanged.
