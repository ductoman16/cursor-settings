# Implement Jira Ticket Command

Autonomously implement a ticket with the "ai-ready" tag in Jira.

## Usage

``` cursor-agent
/implement-ai-ready-jira-ticket [optional-epic-or-project]
```

## Parameters

- `optional-epic-or-project`: Optional Jira Epic or Project to filter by (e.g., DEV-123)

## Prerequisites

- Atlassian MCP: For retrieving and updating ticket information.

## Workflow

### Find the next ai-ready ticket

1. Query Jira using the Atlassian MCP to find the next ticket with the following criteria
    a. Must have the "ai-ready" tag
    b. Must have no open blocking tickets
    c. If provided, must be a child of the provided Jira Epic or Project
2. Order the tickets by priority
3. Choose a single ticket with the highest priority

### Implement the ticket

1. Analyze the requirements in the ticket description
2. View the attached Figma design via the Figma MCP, if available
3. Determine if all of the required repositories for the change are available in your current working directory. If not, STOP HERE and inform the user.
4. Assign me to the ticket, and mark the ticket as "In Progress".
5. Create a new branch off main, starting with the ticket number.
6. Make the necessary code changes, following existing codebase patterns.
7. Write comprehensive tests and ensure they exercise the functionality.
8. Review all outstanding git changes, looking for functional correctness, duplicated code, opportunities for refactoring, and code standard adherence. Fix any issues.
9. Commit the changes, push the branch, and create a PR to main.
10. Poll the status of the Azure DevOps build for the PR, until it succeeds. If it does not succeed, fix any errors.
