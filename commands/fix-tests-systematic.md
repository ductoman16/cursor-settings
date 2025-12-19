# Fix Tests Command (Systematic)

Run the appropriate test command and fix all failing tests, going through them one by one with user confirmation at each step.

## Workflow

- Run the appropriate test command (NEVER use --no-build or equivalent to skip building)
- Locate the first failing test, and announce that you are fixing it
- If you encounter anything that isn't provided or needs clarification, STOP and ask the user for help
- Fix the test, keeping in mind that it may be either the test case itself, or the code under test, that is broken
- After fixing each individual test, STOP and ask the user if you should proceed to the next failing test
- Repeat until no test failures
- You may run subsets of the tests while iterating, but always run ALL tests before saying you're finished
