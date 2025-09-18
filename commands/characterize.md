# Characterization Tests Command

Create characterization tests for this project to capture current behavior.

## Workflow

- Run a command to calculate code coverage for the whole repo
- Identify the file with the lowest code coverage. This MUST be a file with logic, not just a data-only object. DO NOT write tests that confirm that built-in language features like auto-properties work correctly.
- Create characterization tests for it - tests should pass for the current behavior of the code, whether the behavior is correct or not.
- ONLY create/modify test files
- Re-run code coverage command
- Output a table of the relevant files with the lowest coverage
- Ask the user before moving on to the file with the next lowest coverage
