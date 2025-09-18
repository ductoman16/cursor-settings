# Objectify Command

Analyze this class for opportunities to refactor it into a more object-oriented design.

## Usage

``` cursor-agent
/objectify [class-file-path]
```

## Parameters

- `class-file-path`: Path to the class file to analyze

## Analysis Areas

- Identify procedural or utility patterns
- List domain concepts represented in the class
- Suggest new objects or value types to encapsulate data and behavior
- Highlight where instance state or methods could replace parameter passing
- Be specific and reference OO principles or anti-patterns where relevant

## Output

1) Create a list of numbered recommendations based on the above analysis.
2) Ask the user which recommendations they would like to implement.
3) Create a task list, and begin implementing fixes, one by one.
