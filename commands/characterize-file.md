# Characterization Tests Command (File)

Create characterization tests for one or more specified files.

## Usage

``` cursor-agent
/characterize-file [files]
```

## Parameters

- `files` (required): One or more files to create characterization tests for.

## Workflow

1) Test Creation

    - Create characterization tests for the specified file(s) - tests should pass for the current behavior of the code, whether the behavior is correct or not.
    - ONLY create/modify test files
    - Run a code coverage command
    - Output a table showing the new coverage for the tested files

2) Bug Identification

    - Based on the tests created and their results, list out a numbered list of potential bugs found in the code
    - DO NOT change the existing logic - only identify bugs through testing
    - Present the bugs as a numbered list with clear descriptions

3) Stop

    - The workflow stops after completing bug identification
