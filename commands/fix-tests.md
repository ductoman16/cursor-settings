# Fix Tests Command

Run the appropriate test command and fix all failing tests.

## Workflow

- Run the appropriate test command (NEVER use --no-build or equivalent to skip building)
- Locate the first failing test, and announce that you are fixing it
- Fix the test, keeping in mind that it may be either the test case itself, or the code under test, that is broken
- Repeat until no test failures
- You may run subsets of the tests while iterating, but always run ALL tests before saying you're finished
