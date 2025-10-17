# Implement Jira Ticket Command

Review a ticket for completeness.

## Usage

``` cursor-agent
/review-jira-ticket [ticket-number]
```

## Parameters

- `ticket-number`: Ticket number to review

## Prerequisites

- Atlassian MCP: For retrieving and updating ticket information.

## Workflow

1. Retrieve the ticket and understand the details.
2. Determine if there is any information missing from the ticket that would be required for a developer to implement it.
    a. If there is missing information: make an informed guess on what the information should be, and prompt the user to confirm it.
    b. If you cannot make an informed guess: ask the user for clarification.
    c. If the ticket is ready for a developer to implement: Skip to step 3.
3. Output "🎟️✅ Ticket is ready for implementation!"
4. Update the ticket with the "ai-ready" tag.

## Required information

[ ] Affected repositories (usually indicated in square brackets in the title).
    - NOTE: It does not matter what repository the current working directory is. It only matters that the ticket clearly indicates that it is for one or more specific repositories. It does not need to match the current repository.
[ ] Acceptance criteria - should be something that a QA can test/verify
[ ] An attached Figma design if relevant to the ticket
[ ] Blocking tickets: If this ticket has any prerequisites, make sure they are linked properly. If this is a frontend ticket, ensure that all necessary backend endpoint tickets are linked properly.