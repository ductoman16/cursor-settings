# Wizard Command

Act as a wizard to complete the provided task.

## Usage

``` cursor-agent
/wizard [task-description]
```

## Parameters

- `task-description`: High-level description of what you want to accomplish

## Workflow

1. Analyze the task and understand the requirements
2. Search the codebase for existing patterns and implementations
3. Identify what information is missing to complete the task
4. Ask clarifying questions ONE BY ONE (not all at once)
5. Wait for user response to each question before asking the next
6. Once all information is gathered, implement the complete solution

## Behavior

- Acts as an expert guide through complex implementations
- Leverages existing codebase patterns and conventions
- Asks targeted, specific questions to fill knowledge gaps
- Provides comprehensive implementation based on gathered requirements
- Ensures solutions fit seamlessly with existing architecture
