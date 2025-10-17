# Implement Jira Ticket Command

Interactively review all jira stories under a parent work item

## Usage

``` cursor-agent
/review-jira-tickets [parent-id] [project-prefix]
```

## Parameters

- `parent-id`: Required: Parent work item to query
- `project-id`: Required: project identifier to filter by

## Prerequisites

- Atlassian MCP: For retrieving and updating ticket information.

## Workflow

### Find relevant tickets

**** Important: Do NOT query for the parent item directly. This will throw an out of memory error. ****

//TODO: Come up with an exact query template for the AI to use
1. Query using JQL for stories under the provided parent (use `portfolioChildIssuesOf` to include children of children, etc).
2. Only include Story and Sub-task item types
3. Do NOT include tickets have the "ai-ready" tag
4. Only include tickets that are un-started
5. Skip tickets that are obviously not for engineers (QA tickets, Design tickets, etc)

### Review each ticket

Walk through each ticket ONE BY ONE. For each ticket:

1. Retrieve the ticket and understand the details.
2. Determine if there is any information missing from the ticket that would be required for a developer to implement it.
    a. If there is missing information: make an informed guess on what the information should be, and prompt the user to confirm it. 🛑 WAIT for the user to respond.
    b. If you cannot make an informed guess: ask the user for clarification. 🛑 WAIT for the user to respond.
    c. If the ticket is ready for a developer to implement: Skip to step 3.
3. Output "🎟️✅ Ticket is ready for implementation!"
4. Update the ticket with the "ai-ready" tag.
5. Proceed to the next ticket

## Required information

[ ] Affected repositories (usually indicated in square brackets in the title).
    - NOTE: It does not matter what repository the current working directory is. It only matters that the ticket clearly indicates that it is for one or more specific repositories. It does not need to match the current repository.
[ ] Acceptance criteria - should be something that a QA can test/verify
[ ] An attached Figma design if relevant to the ticket
[ ] Blocking tickets: If this ticket has any prerequisites, make sure they are linked properly. If this is a frontend ticket, ensure that all necessary backend endpoint tickets are linked properly.