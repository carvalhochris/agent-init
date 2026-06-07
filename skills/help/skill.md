# Help Skill

Universal help skill for any agent-powered project.

## Skill Definition

**Name**: help
**Trigger**: "help", "guide", "onboarding", "how do I use this project"
**Purpose**: Guide users on how to work with this agent-ready project

## What This Project Provides

### Universal Structure
Every project initialized with agent-init includes:

- **AGENTS.md** - Agent definitions and capabilities (you are reading this file)
- **worklog.md** - Log of work completed by agents
- **README.md** - Project documentation
- **.agents/config/** - Agent configuration files
- **.agents/prompts/** - Agent prompt templates
- **skills/** - Reusable skills for this project

### Working with This Project

1. **Read AGENTS.md** - Understand your agents' purpose and capabilities
2. **Check worklog.md** - See what has been done and what's in progress
3. **Review .agents/prompts/system.md** - Understand agent instructions
4. **Explore skills/** - Find useful skills for common tasks

### Skills Available

Skills are defined in `skills/` and registered in `skills/index.json`.

## Supported Harnesses

This project works with:
- **opencode**: Configure via `opencode.json`
- **codex**: Standard agent conventions
- **claude code**: Standard agent conventions

The universal structure works regardless of which harness you use.

## Conventions

- Log significant work in worklog.md
- Update AGENTS.md when agent purpose changes
- Keep skills in skills/ directory
- Register new skills in skills/index.json

## Getting Help

To get help from an agent in this project:
1. Reference AGENTS.md to understand agent capabilities
2. Check skills/ for available specialized workflows
3. Review worklog.md to see past work and patterns