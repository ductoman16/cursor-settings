# Review Test Code for Best Practices

Review the provided test files for compliance with the FIRST principles, provide an output for each letter in the acronym.

- Fast
- Independent
- Repeatable
- Self-validating
- Thorough

Additionally, review the following points and provide an output for each:

1) Does each test method assert one thing? Multiple assert statements are ONLY allowed if they are asserting different portions of one logical fact.
2) Are there any test cases missing that are critical for the responsibilities of this class, and only this class?
3) Are there any test cases that test responsibilities that are OUTSIDE of this class?
4) Is there any duplicated setup code that could be refactored out?
5) Do each of the test case names accurately reflect the scenario under test?

- Focus on any issues found, do not simply praise the code.
- Please identify any risks, no matter how small.
- Please keep reviews CONCISE.

## Usage

``` cursor-agent
/review-tests [optional-file-path]
```

## Parameters

- `file-path` (optional): Specific file to analyze. If not provided, analyzes the entire codebase.

## Output

1) Create a list of numbered recommendations based on the above analysis.
2) Ask the user which recommendations they would like to implement.
3) Create a task list, and begin implementing fixes, one by one.
