# Implement Jira Ticket Command

Autonomously implement the provided Jira ticket with full development workflow.

## Usage

``` cursor-agent
/implement-jira-ticket [jira-ticket-number]
```

## Parameters

- `jira-ticket-number`: The Jira ticket to implement (e.g., DEV-123)

## Prerequisites

- Atlassian MCP: For retrieving and updating ticket information.

## Workflow

1. Analyze the requirements in the ticket, mark it as "In Progress".
2. Create a new branch off main, starting with the ticket number.
3. Make the necessary code changes, following existing codebase patterns.
4. Write comprehensive tests and ensure they exercise the functionality.
5. Review all outstanding git changes, looking for functional correctness, duplicated code, opportunities for refactoring, and code standard adherence. Fix any issues.
6. Ask the user if you should commit changes.
7. Commit the changes, push the branch, and create a PR to main, following all standards listed above.
8. Poll the status of the Azure DevOps build for the PR, until it succeeds. If it does not succeed, fix any errors, and ask the user before committing changes.
