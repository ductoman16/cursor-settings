# Pipeline Command

Fix errors in this repository's build pipeline.

Use the Azure CLI to find the build with the provided BuildId (find the latest build run for this repository if none provided). Fix any errors you find in the failing build steps.

## Usage

``` cursor-agent
/fix-pipeline [optional-build-id]
```

## Parameters

- `build-id` (optional): Specific build to analyze. If not provided, finds the latest build for this repository.

## Behavior

1) Determine the type of build pipeline used by this repository.
2) Use CLI commands or MCP servers to find information on the most recent build (or specific build if ID is provided).
3) If authentication is required, stop and give the user instructions on how to authenticate.
4) Analyze and fix the root causes of any build failures
5) Re-run build if necessary to verify fixes.
