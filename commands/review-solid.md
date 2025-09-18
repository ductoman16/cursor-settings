# SOLID Principles Analysis Command

Search the specified file (or the entire codebase if not specified) for violations of the SOLID principles. Provide an output for each letter in the acronym, and create a menu of specific recommendations based on the analysis.

## Usage

``` cursor-agent
/review-solid [optional-file-path]
```

## Parameters

- `file-path` (optional): Specific file to analyze. If not provided, analyzes the entire codebase.

## SOLID Principles

- **S**ingle Responsibility Principle: Classes should have one reason to change
- **O**pen/Closed Principle: Open for extension, closed for modification  
- **L**iskov Substitution Principle: Derived classes must be substitutable for base classes
- **I**nterface Segregation Principle: Clients shouldn't depend on interfaces they don't use
- **D**ependency Inversion Principle: Depend on abstractions, not concretions

## Output

1) Create a list of numbered recommendations based on the above analysis.
2) Ask the user which recommendations they would like to implement.
3) Create a task list, and begin implementing fixes, one by one.
