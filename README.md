# QA Agentic Framework

A reusable AI-powered QA Agentic Framework designed to orchestrate specialized AI agents and reusable skills to support software testing activities.

## Overview

The framework provides a modular approach to AI-assisted Quality Assurance by separating agent responsibilities from reusable testing workflows.

Instead of relying on a single AI agent to handle all testing activities, the framework uses specialized agents that collaborate through an Orchestrator to perform specific QA tasks.

## Key Features

- **Agent-Based Architecture:** Specialized agents with clearly defined roles and responsibilities.
- **Reusable Skills:** Modular testing workflows that can be discovered and applied based on the requested task.
- **Flexible Orchestration:** Delegates tasks to appropriate agents without enforcing a fixed QA lifecycle.
- **Exploratory Testing:** Explores application functionality and discovers potential test scenarios.
- **Test Design:** Generates structured and prioritized test scenarios.
- **Test Execution:** Executes existing scenarios and records PASS, FAIL, and BLOCKED results.
- **Defect Reporting:** Supports reporting confirmed defects with supporting evidence.

## Architecture

The framework is organized into three main components:

### 1. Agents

Agents are responsible for coordinating and performing specialized QA tasks.

- **QA Orchestrator:** Understands user requests, discovers agents, delegates tasks, and coordinates results.
- **Test Designer:** Discovers and applies relevant skills to design test scenarios.
- **Executor:** Manages test execution and reports results.
- **Bug Reporter:** Handles defect reporting.

### 2. Skills

Skills provide reusable instructions and workflows that agents can discover and apply when needed.

Current skills include:

- Exploratory Testing
- Test Execution
- Confirmation

### 3. Guidelines

Contains setup and configuration guidance for the framework and its integrations.

## Project Structure

```text
agent/
├── Agents/
│   ├── Orchestrator.md
│   ├── Designer.md
│   ├── Executer.md
│   └── Bug_Reporter.md
├── Guidelines/
├── Skills/
│   ├── Exploratory.md
│   ├── Execution.md
│   └── Confirmation.md
├── Reports/
├── Requirement/
├── .gitignore
└── README.md
```

## Tools & Integrations

The framework is designed to work with available AI development environments and MCP integrations.

Examples include:

- GitHub Copilot
- Playwright MCP for Web Application Testing
- Mobile MCP for Mobile Application Testing
- Atlassian MCP for Jira integration

Integrations are configurable based on the target environment and project requirements.

## Workflow

A typical workflow may include:

1. Submit a QA task to the Orchestrator.
2. Discover and select the appropriate Agent.
3. Discover and apply the relevant Skill.
4. Perform the requested QA activity.
5. Validate generated outputs and report results.

The workflow is flexible. Users can request individual QA activities without following a mandatory sequence.

## Design Principles

- Modularity and reusability.
- Separation of agent responsibilities and skill workflows.
- Tool and platform flexibility.
- Evidence-based testing.
- No invented requirements or expected results.
- Human review and approval when required.

## Project Status

**Under Active Development**

This project is continuously evolving as new agents, skills, and integrations are introduced.

## Author

**Ezzeldeen Elkordy**
