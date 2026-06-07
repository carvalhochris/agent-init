# Conventions Skill

Coding and collaboration conventions for agent-powered projects.

## Skill Definition

**Name**: conventions
**Trigger**: "conventions", "standards", "best practices", "coding rules"
**Purpose**: Provide project conventions for consistent agent collaboration

## File Organization

```
project/
├── AGENTS.md           # Agent definitions (primary source of truth)
├── worklog.md          # Chronological work log
├── README.md           # User-facing documentation
├── skills/             # Reusable skills
│   └── index.json      # Skill registry
├── .agents/
│   ├── config/         # Agent configurations (JSON)
│   └── prompts/        # System prompts (Markdown)
└── [project files]     # Your actual code
```

## Agent Conventions

### When Working on Code
- Read existing code before modifying
- Preserve code style and formatting
- Add comments for non-obvious logic
- Update AGENTS.md if agent behavior changes

### When Logging Work
- Use ISO date format: YYYY-MM-DD
- Add entries to worklog.md for significant changes
- Include context: why, not just what

### When Creating Files
- Follow project naming conventions
- Place files in appropriate directories
- Update relevant documentation

## Skill Conventions

### Creating a Skill
1. Create `skills/<skill-name>/skill.md`
2. Add entry to `skills/index.json`
3. Include triggers, purpose, and steps

### Skill Format
```markdown
# Skill Name

**Name**: skill-name
**Trigger**: keywords that activate this skill
**Purpose**: what this skill does

## Steps
[Step-by-step instructions]
```

## Commit Conventions

- Commit related changes together
- Write clear commit messages
- Reference issues/tickets when applicable

## Notes

- Conventions apply to all agents working in this project
- Any agent can update conventions via worklog
- Major changes require AGENTS.md update