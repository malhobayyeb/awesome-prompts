# 🤖 AGENTS.md – Agent Configuration & Prompt Engineering Standards

This document defines how CLI-based agents should behave inside the `awesome-prompts` repository.

It covers both:
- 📐 Prompt structure and file layout
- 🧠 How to generate high-quality, optimized prompts — as done by Prompt Optimizer

---

## 🧩 What Is This Repo?

This is a modular prompt library to support test engineering, reverse documentation, requirement analysis, code coverage, refactoring, and architecture review across any tech stack.

Your job as an agent is to generate prompts that are:

- Repeatable
- High-quality
- Stack-aware or stack-agnostic as needed
- Compatible with automated or manual workflows
- Never vague, fragile, or overly generic

---

## ✅ Prompt Structure

Each prompt should follow this exact Markdown layout:

```markdown
### ✅ Prompt Title – Clear and Actionable

> [Direct, precise instruction]  
> **Scope:** [What can be read/modified/ignored? What folder boundaries must be respected?]

```

Use this layout exactly whenever you add or update prompts in this repo.

🧠 How to Think Like Prompt Optimizer

You must follow these exact prompt engineering principles:

🟢 1. Write for Action

Prompts should start with a clear imperative instruction:

❌ “Can you check the test coverage?”
✅ “Analyze the test files and identify uncovered code paths. Document your findings in…”

🟢 2. Be Specific

Prompts must clarify:

What is being scanned? (tests, source code, docs?)

What is the output? (checklist, file, summary?)

What is the format? (markdown, plain text?)

Where does it go? (e.g., docs/tests/uncovered.md)

🟢 3. Declare Scope Explicitly

Every prompt must define access like:
**Scope:** Only read from the `tests/` directory. Do not modify any other files.

Scope rules may include:

✅ Only read or write within specific folders

❌ Do not touch production code

❌ Do not operate on ignored files (respect .gitignore)

🟢 4. Avoid Assumptions About Tech Stack

Unless the folder explicitly indicates the stack (e.g., /laravel/, /kmp/), the prompt must be framework-agnostic.

🟢 5. Write for Repeatability

Prompts must be reusable and deterministic. Avoid:

“As needed”

“Etc.”

“Based on your setup”

Do specify:

File names

Output format

Fixed structure

🟢 6. Support Sequential Workflows

For multi-step processes, break the prompt into clearly numbered steps:

## 🔄 Reverse Engineering Requirements Sequence

### ✅ Step 1 – Analyze Tests

> Scan all test cases to identify behaviors...

### ✅ Step 2 – Analyze Code

> Read the source code and identify...

### ✅ Step 3 – Write Epics

> Create a new file named...

🟢 7. Format Human-Friendly Output

When generating or documenting output:

Use - [ ] markdown checkboxes

Use clear user stories:
"As a [role], I want to [action] so that [goal/value]."

🟢 8. Avoid AI Clichés

Do not include:

“As an AI model…”

“Think step by step…”

“Can you please…”

Instead, use direct, declarative language.

✅ Prompt Examples

### ✅ Scan for Uncovered Logic

> Analyze all test files and identify logic branches or business rules that are not covered.  
> Output your findings in `docs/tests/uncovered.md` using markdown checkboxes.  
> **Scope:** Only read from `tests/`. Do not modify source code.


### ✅ Generate Agile User Stories from Code

> Analyze source code and tests. Create `docs/tests/agile-requirements.md` with grouped epics and user stories.  
> Format: "As a [role], I want to [action] so that [outcome]."  
> **Scope:** Read-only access to code and test files. Only write to `docs/tests/`.

🧠 Summary

Agents must:
- Follow strict formatting
- Use concise, directive language
- Declare scope and purpose in every prompt
- Think like a professional prompt engineer, not a chatbot
- Reuse structure, style, and quality from Prompt Optimizer
