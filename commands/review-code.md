# Code Review Command

Provide a thorough code review of the provided file, or all changes found via git status if a single file is not provided. If given a ticket or task number, or if the current branch begins with a ticket or task number, review the current changes against the ticket's requirements.

Do NOT go easy on the user, and don't just praise the code. Find ANY issues, no matter how trivial.

## Usage

``` cursor-agent
/review-code [optional-file-path] [optional-ticket-number]
```

## Parameters

- `file-path` (optional): Specific file to review. If not provided, reviews all changed files from git status.
- `ticket-number` (optional): Ticket or task number containing the requirements for the task at hand.

## Output

1) Create a list of numbered recommendations based on the above analysis.
2) Ask the user which recommendations they would like to implement.
3) Create a task list, and begin implementing fixes, one by one.
