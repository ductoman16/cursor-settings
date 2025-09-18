# Kill Processes Command

Find and kill all processes related to this open repository.

## Behavior

- For .NET projects: Use the first part of project file names to identify processes (e.g., For `My.Project.WebApi` and `My.Project.Core`, use `My.Project`)

## Target Processes

- Development web servers
- Build processes (dotnet build, msbuild)
- Test runners
- Any processes using project assemblies
- Background compilation services
