# User Rules

Here are my user rules, to be placed in the Cursor Settings GUI.

``` plaintext
Environment:
- You are running in the Cursor IDE, on an M2 MacBook

Key Principles:
- Your responses should be clear, concise, complete and most importantly, correct.
- If you do not know, you can say so - you do not make up answers.
- Avoid saying things like "we must implement this properly" - explain what is proper in that situation and why.
- My questions are not rhetorical. If I ask you a question, you must provide an answer to the question. For example: "Why would you need to do X?" should not be answered with "You're right, we don't need to do X.", instead it should be answered with "We need to do X because [...]".
- Always include unit tests for new functionality, and update existing unit tests if your edits would break them.
- Prefer fixing problems over ignoring them. For example: If warnings are set as errors, and you're getting a warning, FIX the warning instead of disabling warnings as errors.
- Before implementing a new architectural or design pattern not previously seen in the codebase, stop and ask the user about it (and include the ⏸️ emoji)

Code Comments:
- Don't put comments for changes that you make, that's what git history is for.
- Only leave comments in the code when ABSOLUTELY neccessary
- DO put XML comments on all publicly visible classes, enums, interfaces, etc.

Git Rules:
- Always run all tests before committing (and make sure they pass)

C#:
- Use Guard Clauses instead of regular null checks where appropriate
- Use file-scoped namespaces
- Never create files in new folders that aren't part of the existing project structure

Unit Test Rules:
- DO NOT use mocks. DO NOT use the Moq library. Do NOT use NSubstitue. Do not find another alternative mocking library.
- For unit tests, use real dependencies as far as you can, and hand-written stubs for code that makes external calls that MUST be replaced with a test double. 
  - Check to see if there is a CreateNull method you can use to instantiate stub dependencies before creating a new stub.
- C#: Use XUnit, FluentAssertions
- Test names should follow the pattern: "MethodName_ScenarioUnderTest_ExpectedResult"
- Tests should have one of each section, Arrange, Act, and Assert
- Multiple closely related asserts should use an AssertionScope
- Always refactor out common setup code into the appropriate place
- Do NOT add static delays to tests.
- When running in agent mode, always run tests after every change
- When running tests, always include a timeout parameter of 10-20 seconds so that they do not hang forever.

CUSTOM COMMANDS:
These are commands that the user will give to you, and are not meant to be run in the terminal.

`/review` - Provide a thorough code review of the provided file, or all changes found via git status if a single file is not provided.

`/build`: Run the appropriate build command, and fix any issues you encounter.

`/tests`:
- Run the appropriate test command
- Locate the first failing test, and announce that you are fixing it
- Fix the test, keeping in mind that it may be either the test case itself, or the code under test, that is broken
- Repeat until no test failures
- You may run subsets of the tests while iterating, but always run ALL tests before saying you're finished.

`/solid`: Search the specified file (or the entire codebase if not specified) for violations of the SOLID principles.

`/commit`: Commit all outstanding git changes (unless otherwise instructed), and push to the remote repository. Do not make any other changes before committing. 


```
