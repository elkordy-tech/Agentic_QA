---
name: exploratory-testing
description: Explores web and mobile applications and generates Test Scenarios based on exploration findings.
---

# Role

Explore the specified application module to understand its functionality, discover workflows and dependencies, and document actual application behavior.

# Inputs

- Target Application / Module.
- Target Page or URL.
- Available MCP tools: Playwright MCP for Web and Mobile MCP for Mobile.

# Workflow

## 1. Explore the Application

- Navigate to the specified page using the appropriate MCP.
- Inspect visible UI components and interactive elements.
- Explore buttons, forms, dropdowns, tables, filters, tabs, modals, and navigation.
- Interact with the application to understand validations, workflows, state changes, and dependencies.
- Verify behavior through actual interaction. Do not assume unverified functionality.
- Explore relevant features and workflows within the specified scope.

## 2. Classify Findings

Use these classifications:

- **[Verified]:** Behavior directly confirmed through actual application interaction.
- **[Inferred]:** Logical assumption based on observed application behavior.
- **[Unknown]:** Behavior that cannot be confirmed due to missing information, access, or evidence.

Do not treat observed application behavior as approved expected behavior.
Clearly distinguish verified behavior from assumptions and unknowns.


## 3. Generate Test Scenarios

Cover all applicable areas, including:
1. Positive
2. Negative
3. Boundary/edge
4. Main/basic flow
5. Alternate flow
6. Exception flow
7. Integration
8. Data/database (CRUD, integrity, persistence)
9. Business rule/logic
10. Input validation
11. Error handling
12. State transition
13. Workflow/end-to-end
14. Role-based/permission
15. Recovery


Rules:

- Cover all observable features.
- Do not force irrelevant testing types.
- Avoid duplicate scenarios.
- Do not limit the number of scenarios.
- Write short, clear, actionable statements starting with "Verify that...".
- Assign High, Medium, or Low priority.
- Identify scenarios based on inferred or unconfirmed behavior.

## 4. Test Oracle

- Use directly observable application behavior to understand UI interactions and basic functionality.
- Do not assume that the current implementation represents the correct business behavior.
- Record actual application behavior accurately.
- Do not invent expected results or business rules.
- When a scenario depends on an unknown business rule, document the observed behavior and mark the expected behavior as Unknown
- Do not report behavior as a confirmed defect unless there is sufficient evidence that it violates an established expectation.

# Output

" - [ ] " Scenario type | Scenario description | ( High / Med / Low )

## Rules:

- Write scenarios as one-line "Verify that..." statements.  
- Use simple, easy English. Short sentences.  
- Coverage over Quantity: Prioritize 100% testable requirement and feature coverage over the number of test scenarios. Do not limit scenarios to a fixed number.


## Output and Reporting Rules
- Base output directory: ./Reports/Exploratory/
- Generate one unique folder for every execution using: Project_Date_Time.
- Example: TaskFlow_2026-11-18_0831.
- Each execution folder must contain:
{folder_name}/
├── Report.md

### Report
- Generate exactly one Report.md per execution.
- Include all explored Modules and Features, Total Scenarios, Coverage Gaps and Limitations.


# Completion Criteria

Complete the available exploration, generate relevant Test Scenarios, and report remaining unknowns, coverage gaps, and limitations.