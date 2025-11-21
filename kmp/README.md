## Prompts

### ### Finding Gaps Task Sequence

✅ Prompt 1

```md
Manually scan all test directories across the project (e.g., commonTest/, androidTest/, iosTest/, etc.). Analyze the structure, coverage themes, and types of tests implemented. Identify conventions, focus areas, and module-level gaps in coverage.
Scope: Only read and analyze test code. Do not edit or modify any files. Exclude any directories or files listed in .gitignore.
```

✅ Prompt 2

```md
Cross-reference all existing tests with the actual source code of the KMP project. Identify uncovered logic paths, shared UI behaviors, business rules, state machines, user flows, and edge cases.
Ignore any platform-specific test logic that is intentionally excluded from shared code.
Scope: Do not edit or modify any files. Respect .gitignore. Laravel/Nova-specific logic does not apply.
```

✅ Prompt 3

```md
Write a detailed checklist of uncovered logic paths, shared behaviors, business rules, or UI states to the file docs/tests/uncovered.md.
Use markdown task list format (- [ ]) for each item. Be as specific and actionable as possible so each task can be implemented without further clarification.
Scope: Only write to the docs/tests/ directory. Do not create or modify any files elsewhere in the project.
```

### Confirming Gaps – KMP Version

✅ Prompt 1

```md
Open the file docs/tests/uncovered.md and read through the list of uncovered items. Understand each item’s intent in relation to the project's modules and shared logic.
Scope: Only read from docs/tests/. Do not modify any files.
```

✅ Prompt 2

```md
Cross-reference each item in docs/tests/uncovered.md with the test files in all modules (e.g., common, Android, iOS). Confirm whether each item has already been fully covered.
Scope: Only scan test code. Do not edit or modify any files. Respect .gitignore entries.
```

✅ Prompt 3

```md
Remove any items from docs/tests/uncovered.md that are already fully covered in existing test files. Keep only valid and untested items.
Scope: Only modify files inside docs/tests/. Do not change or touch any files outside that folder.
```

### Implementing Uncovered Tests – KMP Version

✅ Prompt 1

```md
Read the list of uncovered items from docs/tests/uncovered.md. Prepare to implement the first unchecked item as a meaningful test.
Scope: Only read this documentation file. Do not modify or edit anything outside of docs/tests/.
```

✅ Prompt 2

```md
Pick the first unchecked item from docs/tests/uncovered.md. Implement a meaningful test case for it in the appropriate module (e.g., commonTest, androidTest, etc.) based on the logic involved.
Do not run the entire test suite. Only run the test(s) related to the implemented item to confirm it works as expected.
After successful implementation, update docs/tests/uncovered.md by marking the item as checked (- [x]).
Scope: Only modify files in the tests directories and docs/tests/. Do not make changes to any production source files.
```
