# Merge to Canary Command

Fast forward merge the main branch into the canary branch

## Behavior

0. If there are any outstanding changes in this repo, STOP HERE and inform the user.
1. Locate an existing PR in github going from main to canary. If none exists, STOP HERE and inform the user.
2. Checkout the 'main' branch
3. Pull the 'main' branch
4. Checkout the 'canary' branch
5. Pull the 'canary' branch
6. Run `git merge --ff-only main`
7. Push the canary branch
8. Find all Jira tickets numbers that are associated with the PR, and update them to "Ready To Test" state
