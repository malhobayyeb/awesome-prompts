# Laravel Prompt Pack

Use this folder when you need to inspect a Laravel application's tests and identify missing business logic coverage. The prompts focus on the conventional `tests/` directory and related source code. The [repository overview](../README.md) explains how this pack complements the others.

## Workflow outputs

- Document uncovered scenarios in `tests/uncovered.md` inside the Laravel project you are reviewing.
- Any added tests should live under the project's `tests/` directory as directed in the prompts.

---

## Prompts

### Finding Gaps Task Sequence

✅ Prompt 1

```md
Manually scan and analyze the contents of the tests/ folder to understand the existing test structure, logic coverage, and types of tests written. Focus on identifying patterns, conventions, missing coverage, and the relationship between test cases and application logic.
Scope: Only operate inside the tests/ folder. Do not edit or modify any files outside of this folder.
```

✅ Prompt 2

```md
Cross-reference the application codebase with the tests/ directory. Manually identify uncovered business logic, code paths, feature flows, and edge cases that currently have no corresponding tests. Do not rely on previous coverage files or test execution.
Respect .gitignore and exclude ignored files or directories.
Ignore Laravel Nova and all of its related code.
Do not make any edits to the codebase.
Scope: Only use data from inside the tests/ directory and source code. Do not edit any files.
```

✅ Prompt 3

```md
Based on your analysis, create a detailed checklist of uncovered logic, business rules, and edge cases. Write this list to a file named tests/uncovered.md using markdown checkbox format (- [ ]). Each entry should clearly describe what needs to be tested and be actionable.
Scope: Operate strictly inside the tests/ folder. Do not modify or edit any files outside this folder.
```

### Confirming Gaps Task Sequence

✅ Prompt 1

```md
Open the tests/uncovered.md file and read through the checklist of uncovered items. Interpret each item in context of the application logic and testing structure.
Scope: Operate strictly inside the tests/ folder. Do not modify or edit any files outside this folder.
```

✅ Prompt 2

```md
Cross-check each item listed in tests/uncovered.md with the actual implemented tests inside the tests/ folder. Determine whether any items are already fully covered by existing test cases.
Scope: Operate strictly inside the tests/ folder. Do not modify or edit any files outside this folder.
```

✅ Prompt 3

```md
For each item in tests/uncovered.md, confirm whether the logic or scenario is already tested. If it is, remove that item from the file to clean up false positives. Retain only the confirmed gaps that are not covered by existing tests.
Scope: Operate strictly inside the tests/ folder. Do not modify or edit any files outside this folder.
```

### Implementing Uncovered Tests Task Sequence

✅ Prompt 1

```md
Open the tests/uncovered.md file and review the list of uncovered items. Carefully read and interpret each checklist entry to understand the required logic, behavior, or edge case that needs to be tested.
Scope: Operate strictly within the tests/ directory. Do not edit or modify any files outside this folder.
```

✅ Prompt 2

```md
From the tests/uncovered.md file, pick the first unchecked item. Implement a corresponding and meaningful unit or feature test for it inside the tests/ directory.
Do not run the full test suite—only run the test(s) directly related to this item to confirm its correctness.
Once the item is successfully tested, update the tests/uncovered.md file by marking it as checked (- [x]).
Scope: Operate strictly within the tests/ directory. Do not modify or edit any files outside this folder. Avoid shallow or artificial test coverage.
```
