✅ Prompt 1 – Scan all test files to infer system behaviors

Analyze all test files across the project—unit, integration, feature, or system tests.
Identify what each test validates in terms of business logic, user interaction, or system behavior.
Extract high-level insights about functional requirements implied by the existing tests.
Scope: Read-only access to test files. Do not modify or generate new tests. Respect .gitignore or any project-specific exclusion rules.

✅ Prompt 2 – Analyze source code to understand the system

Explore the source code of the application to understand how it works, what it does, and what features it implements.
Focus on core components such as logic modules, UI flows, service layers, state management, validation logic, and any domain-specific behaviors.
Scope: Read-only access to source code. Do not modify or create any files. Respect ignore rules.

✅ Prompt 3 – Generate initial Agile epics and user stories

Based on the understanding of tests and source code, create a structured file called docs/tests/agile-requirements.md containing:

Epics: Major themes or functional domains

User Stories: Written in the format:
"As a [user type], I want to [do something] so that [value achieved]."
Group user stories under their relevant epics. Ensure each story is focused, testable, and actionable.
Scope: Only write to docs/tests/agile-requirements.md. Do not create or modify any other files.

✅ Prompt 4 – Identify missing or implicit requirements

Compare the generated requirements with actual system functionality. Identify any behaviors, workflows, or logic paths that are implemented but not yet described in the user stories.
These represent gaps between reality and documented intent.
Scope: Read-only access to code and tests. Only update agile-requirements.md with newly discovered requirements.

✅ Prompt 5 – Add missing epics or stories to the requirements file

For each uncovered behavior or logic gap, write new user stories (and epics if needed).
Append them to docs/tests/agile-requirements.md under appropriate sections.
Ensure the new stories follow consistent formatting and are not redundant with existing ones.
Scope: Only edit docs/tests/agile-requirements.md. Do not change any other files.

✅ Prompt 6 – Cross-check each story for implementation or test coverage

For every user story in agile-requirements.md, determine if it is:

Fully implemented in code

Covered by an existing test

Partially implemented

Not implemented at all
Optionally, tag each story with a status (e.g., ✅ implemented, ❌ missing, 🧪 tested only).
Scope: Read-only access to code and tests. Only modify agile-requirements.md for tagging.

✅ Prompt 7 – Detect orphaned code not linked to any story

Find any parts of the source code or tests that are not referenced by any user story or epic.
List these as orphaned or undocumented functionality. Suggest whether they should be removed, explained, or integrated into a new story.
Scope: Read-only access to code and tests. Only write summary findings or updates to agile-requirements.md.

✅ Prompt 8 – Refactor and organize requirements

Review the full contents of docs/tests/agile-requirements.md.

Merge duplicates

Clarify vague wording

Ensure consistent format

Reorder for logical flow

Ensure each Epic has a clear theme
The final result should be clean, understandable by stakeholders, and useful for developers and testers.
Scope: Only modify docs/tests/agile-requirements.md. No changes outside this file.

✅ Prompt 9 – (Optional) Annotate stories with priorities or milestones

Add optional metadata to each user story to reflect:

📅 Planned milestone / release

🔼 Priority (High / Medium / Low)

👥 Responsible team
Use consistent formatting and avoid clutter.
Scope: Only update docs/tests/agile-requirements.md. Do not modify any code or test files.

✅ Prompt 10 – Generate summary for product or QA teams

Generate a summary of all Epics and User Stories in agile-requirements.md, organized for non-developers.
Format should be readable by Product Owners, QA Engineers, and business stakeholders.
Optionally, export in simplified markdown or CSV format.
Scope: Only read agile-requirements.md. Output formatted summary separately.