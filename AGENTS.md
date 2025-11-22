# Agent Standards Prompt Pack

## Workflow
Run steps 1️⃣–6️⃣ whenever you add or update prompts in this repo.

### 1️⃣ Load Repo Rules
> Read `AGENTS.md` and the relevant prompt pack before writing anything to ensure alignment with house style.  
> **Scope:** Read-only across the repo; do not modify files yet.

### 2️⃣ Apply the Prompt Layout
> Use the exact prompt format:  
> ```markdown
> ### ✅ Prompt Title – Clear and Actionable
> 
> > [Direct, precise instruction]  
> > **Scope:** [What can be read/modified/ignored? Folder boundaries?]
> ```  
> **Scope:** When writing prompts, edit only the intended prompt pack; do not touch other files.

### 3️⃣ Write Actionable and Specific Instructions
> Start with imperatives, clarify inputs (what to scan), outputs (file/format), and location (target paths). Avoid vague wording and tech-stack assumptions unless explicit in paths.  
> **Scope:** Modify only the prompt text you are authoring; preserve existing content elsewhere.

### 4️⃣ Declare Scope Explicitly
> Include a **Scope** line that defines allowed reads/writes, directories, and prohibitions (e.g., no prod code changes, respect ignores).  
> **Scope:** Edit only the prompt being scoped; do not alter other docs.

### 5️⃣ Support Sequential Workflows
> For multi-step tasks, break work into numbered steps with clear outputs per step to make prompts repeatable and deterministic.  
> **Scope:** Update only the relevant prompt pack; no other files.

### 6️⃣ Format for Agents
> Use markdown checkboxes for checklists, user stories as "As a [role], I want to [action] so that [value]," and avoid AI clichés or filler. Keep language direct and professional.  
> **Scope:** Edit only prompt content; no changes to code or configs.
