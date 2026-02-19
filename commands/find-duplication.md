# Find Duplication

Scan the provided files (or the whole project if no files are specified) for duplicated code relating specifically to domain-level functionality.

Identify where identical or near-identical logic could be safely unified without risking changes that should remain separate due to differing reasons for change. Exclude surface-level similarities that aren't true domain duplication or would be expected to evolve independently.

## Output

1) Create a list of numbered recommendations based on the above analysis.
2) Ask the user which recommendations they would like to implement.
3) Create a task list, and begin implementing fixes, one by one.
