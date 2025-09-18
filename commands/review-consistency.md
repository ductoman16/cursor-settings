# Review Code for Consistency

Analyze the provided files, or outstanding git changes if not provided, or the entire repo if no outstanding changes, for consistency. Ensure similar components use the same strategies and patterns. Provide a report of violations found, and then ask the user which ones you should fix.

## Usage

``` cursor-agent
/review-consistency [optional-file-path]
```

## Parameters

- `file-path` (optional): Specific file to analyze. If not provided, analyzes either outstanding changes or the entire codebase.

## Output

1) Create a list of numbered recommendations based on the above analysis.
2) Ask the user which recommendations they would like to implement.
3) Create a task list, and begin implementing fixes, one by one.
