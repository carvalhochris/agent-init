# Agents

This document defines the agents configured for developing agent-init.

## Value Proposition

agent-init provides a universal framework for starting any project with agents pre-configured. Users choose their preferred harness—opencode, codex, claude code—and get the same opinionated setup out the gate.

**Goal**: One command to rule them all. A consistent agent-ready project structure that works regardless of which AI coding harness you use.

## Primary Agent

**Purpose**: Help build and maintain the agent-init CLI tool

### Responsibilities

- Implement new features for the agent initialization tool
- Fix bugs and improve code quality
- Update documentation and examples
- Ensure the tool works across different project types

### Configuration

- TypeScript project setup
- Node.js CLI development
- Interactive CLI with Inquirer

## Supported Harnesses

- **opencode**: Configured via `opencode.json`
- **codex**: Compatible with standard agent conventions
- **claude code**: Compatible with standard agent conventions

All harnesses share the same universal structure defined below.

## Conventions

- All agent prompts are stored in `.agents/prompts/`
- Agent configurations are in `.agents/config/`
- Skills are defined in `skills/<skill-name>/skill.md`
- Skills are registered in `skills/index.json`
- Agent work is logged in `worklog.md`
- **Always write tests for new features**
- Changes are committed to GitHub regularly

## Universal Project Structure

Every project initialized with agent-init includes:

```
project/
├── AGENTS.md           # Agent definitions and capabilities
├── worklog.md          # Log of work completed
├── README.md           # Project documentation
├── .agents/
│   ├── config/         # Agent configuration files
│   └── prompts/        # Agent prompt templates
└── skills/             # Reusable skills for this project
    └── index.json      # Skill registry
```

This structure is harness-agnostic and ensures any AI coding tool can understand and work with the project effectively.

## Basic Skills

Every agent-init project comes with universal skills:

| Skill | Purpose | Triggers |
|-------|---------|----------|
| help | Project onboarding guide | help, guide, onboarding |
| qa-local | Local QA testing steps | qa-local, qa, test |
| conventions | Coding and collaboration standards | conventions, standards |

Skills are harness-agnostic and work with opencode, codex, and claude code.

---

*This file is maintained by the agents working on agent-init*