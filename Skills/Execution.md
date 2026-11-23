---
name: test-execution
description: Executes existing Test Scenarios using available tools and applications, records results, and captures supporting evidence.
---

# Purpose

Execute existing Test Scenarios and document execution results.

# Inputs

- Existing Test Scenarios.
- Target Application / Module.
- Target Page or URL.
- Available MCP tools: Playwright MCP for Web and Mobile MCP for Mobile.
- Required test data and dependencies.

# Workflow

## 1. Execute Test Scenarios

- Execute scenarios using available MCP tools: Playwright for Web and Mobile MCP for Mobile.
- Execute cross-platform workflows when required.
- Determine the execution result based on whether the application performs the action described in the scenario.
- Continue executing independent scenarios even if another scenario fails.
- Observe the actual application behavior during execution.
- Determine whether the observed behavior satisfies the scenario's objective.
- Do not execute scenarios requiring unavailable dependencies.
- Do not perform destructive or irreversible actions without explicit approval.

## 2. Record Execution Results

Update each scenario directly:

- **PASS:** `- [x] Verify that...`
- **FAIL:** `- [ ] #bug Verify that...`
- **BLOCKED:** `- [ ] Verify that... (Blocked: Reason)`

Rules:

- Do not mark a scenario Pass or Fail without sufficient verification.
- Capture screenshots or other evidence for failed scenarios.
- Document the actual behavior for failed scenarios.
- Document the blocking reason for blocked scenarios.
- Distinguish application defects from environment or MCP tool failures.
- Do not report unconfirmed behavior as a confirmed defect.

## 3. Review Execution Results

- Verify that all executable scenarios have been processed.
- Ensure results match the actual execution evidence.
- Identify remaining blockers and uncovered scenarios.
- Verify that evidence references are valid.
- Do not change results without supporting evidence.

# Rules

- Execute existing Test Scenarios only; do not generate new scenarios.
- Do not skip relevant executable scenarios.
- Do not invent requirements, expected results, or evidence.
- Do not create or modify Jira issues; leave defect reporting to the Bug Reporter Agent.
- Do not modify original requirements or Test Scenario definitions.
- Do not treat environment or tool failures as application defects.
- Never overwrite, reuse, modify, or delete previous execution reports or attachments.

# Output and Reporting

- Base output directory: `./Reports/Execution/`
- Generate one unique folder for every execution using: `Project_Date_Time`.
- Example: `TaskFlow_2026-11-18_0831`.

Each execution folder must contain:

```text
Project_Date_Time/
├── Report.md
└── Attachments/
```

## Report

Generate exactly one `Report.md` per execution.

Include:

- Execution Date and Time.
- Executed Modules and Features.
- Total Scenarios.
- Passed / Failed / Blocked / Not Tested.
- Execution Summary.
- Confirmed Bugs.
- Blocked Scenarios and Reasons.
- Coverage Gaps and Limitations.

## Attachments

- Save screenshots of failed scenarios and related evidence inside the execution's `Attachments/` folder.
- Use meaningful filenames and relative paths in the report.
- Verify that all referenced attachments exist.

## Reporting Rules

- One execution may cover multiple Modules within the same folder.
- Never create separate folders per Module within one execution.
- Never overwrite, reuse, modify, or delete previous execution reports or attachments.
- Create the execution folder and `Attachments/` before execution.
- Calculate all report totals based on actual execution results.
- Count scenarios that were not executed as Not Tested and explain why.

# Completion Criteria

The task is complete when all executable scenarios have been processed, execution results and evidence have been recorded, and remaining blockers, uncovered scenarios, and limitations have been reported.