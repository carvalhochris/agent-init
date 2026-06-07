# agent-init

> **Status**: Very new, very much in development. APIs and conventions may change.

Initialize an agent-repo project with an opinionated setup.

## Overview

`agent-init` is a CLI tool that creates a new project with an agent-ready framework. It sets up the directory structure, configuration files, and documentation needed for agent-powered development.

**Goal**: One command to rule them all. A consistent agent-ready project structure that works regardless of which AI coding harness you use (opencode, codex, claude code).

## Quick Start

```bash
npm install
npm run build
npm link
agent-init
```

## Project Structure

- `AGENTS.md` - Agent definitions and capabilities
- `worklog.md` - Log of work completed
- `skills/` - Reusable skills (help, qa-local, conventions)
- `.agents/` - Agent configuration and prompts

## Development

See [AGENTS.md](./AGENTS.md) for agent configuration.