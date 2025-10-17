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

1. Analyze the requirements in the ticket.
2. Assign me to the ticket, and mark the ticket as "In Progress".
3. Create a new branch off main, starting with the ticket number.
4. Make the necessary code changes, following existing codebase patterns.
5. Write comprehensive tests and ensure they exercise the functionality.
6. Review all outstanding git changes, looking for functional correctness, duplicated code, opportunities for refactoring, and code standard adherence. Fix any issues.
7. Commit the changes, push the branch.
8. Create a PR to main, with a very brief description.
9. Poll the status of the Azure DevOps build for the PR, until it succeeds. If it does not succeed, fix any errors, commit, and repeat until it passes.
