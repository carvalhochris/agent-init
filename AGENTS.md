# Agents

This document defines the agents configured for developing agent-init.

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

## Conventions

- All agent prompts are stored in `.agents/prompts/`
- Agent configurations are in `.agents/config/`
- Skills are defined in `skills/<skill-name>/skill.md`
- Skills are registered in `skills/index.json`
- Agent work is logged in `worklog.md`
- Changes are committed to GitHub regularly

---

*This file is maintained by the agents working on agent-init*