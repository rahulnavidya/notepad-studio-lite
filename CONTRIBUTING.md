# Contributing

Thanks for taking an interest in Notepad Studio Lite.

## Before proposing a change

- Read the [User Guide](docs/USER-GUIDE.md) and [Technical Notes](docs/TECHNICAL-NOTES.md).
- Check the existing behaviour before changing it.
- Keep changes focused and explain the user-facing problem they solve.
- Preserve the single-file app distribution unless a structural change is deliberately proposed and discussed.

## Reporting a bug

Include:

- Browser and operating-system versions.
- Steps to reproduce the problem.
- Expected behaviour and actual behaviour.
- Whether the issue concerns editing, local storage, search, appearance, or file operations.
- Relevant screenshots or a minimal example, with private document contents removed.

## Code changes

The reviewed Pass 3 release is frozen. Changes to application code should be treated as a new version. Do not overwrite the frozen release without recording what changed.

For changes to the HTML application:

1. Keep CSS and JavaScript self-contained unless the project adopts a different distribution model.
2. Do not add remote runtime dependencies without discussing the impact on offline use and privacy.
3. Preserve the separation between browser-workspace autosave and writing to a linked computer file.
4. Keep file-system handles out of serializable workspace data and backups.
5. Preserve error handling for cancelled dialogs, denied permissions, external file changes, and failed writes.
6. Do not weaken or remove a test assertion just to make a suite pass.
7. Record the source hash and QA result for each release candidate.

## Documentation changes

Documentation improvements are welcome. Keep feature claims consistent with the shipped application and identify browser-dependent behaviour clearly.

## Pull requests

Use a descriptive title, explain the reason for the change, list the files changed, and include test results. Small, reviewable pull requests are easier to verify than a giant grab-bag of unrelated changes.
