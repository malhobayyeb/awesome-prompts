# Static Analysis Prompt Pack

## Workflow
Run steps 1️⃣–3️⃣ once to inventory and log findings; repeat 4️⃣ to remediate and track progress.

### 1️⃣ Inventory Static Analysis Setup
> Identify all static analysis tools, linters, formatters, and type checkers configured in the project. Locate config files, ignore lists, and custom rules. Summarize tool versions and entry points.  
> **Scope:** Read-only across the repository; respect ignore settings; do not modify configs or code.

### 2️⃣ Run Static Analysis
> Execute the configured static analysis tools using the project’s checked-in settings.  
> **Scope:** Execute tools; respect ignore settings; do not change source or configs.

### 3️⃣ Log Results
> Record commands, timestamp, and summarized findings from the analysis run into `docs/static-analysis/findings.md`, using markdown checkboxes for actionable items.  
> **Scope:** Write only to `docs/static-analysis/findings.md`; do not modify source or configs.

### 4️⃣ Implement First Remediation Item (Repeatable)
> Open `docs/static-analysis/findings.md`, take the top unchecked item, and fix the root cause (no workarounds or new suppressions/ignores/exclusions/annotations). Apply minimal, behavior-preserving changes that follow existing repo practices, remove related suppressions/ignores/exclusions, and mark the item as checked when verified.  
> **Scope:** Modify only affected source/test files and related suppressions/ignores/exclusions; avoid dependency changes; keep behavior unchanged.
