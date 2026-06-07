# QA Local Skill

Use this skill when the user wants QA steps for testing agent-init locally.

## Skill Definition

**Name**: qa-local
**Trigger**: User invokes "qa-local" or asks for QA steps
**Purpose**: Provide exact, step-by-step QA testing instructions

## QA Workflow

When user invokes "qa-local", load this skill and run the QA workflow using inquirer for multiple choice.

### Pre-commit (automatic)
Before any commit, tests run automatically via husky pre-commit hook. No build needed - vitest handles TypeScript directly.

### QA Steps (One at a time)

**Step 1: Build and Link (manual verification)**
```bash
npm run build && npm link
```
This is for manual QA verification - not required for tests to pass.

**Step 2: Create New Project**
```bash
cd /tmp && rm -rf test-agent-project && agent-init
```
- Project name: `test-agent-project`
- What is this project about?: `A React music player`
- Author name: `Test User`

**Verify:**
- Project directory created at `/tmp/test-agent-project`
- `README.md` contains "A React music player"
- `AGENTS.md` exists
- `worklog.md` exists
- `.agents/config/primary.json` exists
- `.agents/prompts/system.md` exists

**Step 3: Create Project with Defaults**
```bash
cd /tmp && rm -rf my-agent-project && agent-init
```
Press Enter for all defaults.

**Verify:**
- Project created at `/tmp/my-agent-project`
- Default description "General purpose agent-ready project" in files

**Step 4: Overwrite Existing Directory**
```bash
cd /tmp && agent-init
```
- Enter project name: `test-agent-project`
- When asked to overwrite: answer `No`
- Verify it exits gracefully with "Aborted."

**Step 5: Continue Overwrite**
```bash
cd /tmp && agent-init
```
- Enter project name: `test-agent-project`
- When asked to overwrite: answer `Yes`
- Verify files are created in existing directory

**Step 6: Project About Field**
```bash
cd /tmp && rm -rf project-with-desc && agent-init
```
- Project name: `project-with-desc`
- What is this project about?: `Backend API for task management`
- Author: `Dev`

**Verify:**
- `README.md` contains "Backend API for task management"
- `.agents/prompts/system.md` contains "Backend API for task management"
- `worklog.md` contains "Backend API for task management"

**Step 7: Cleanup**
```bash
rm -rf /tmp/test-agent-project /tmp/my-agent-project /tmp/project-with-desc
```

## Implementation Notes

- When user invokes "qa-local", execute this workflow immediately
- Use inquirer to present multiple choice: Pass, Fail, Other
- Give one step at a time
- After each step completion, prompt with "What was the result?" [Pass/Fail/Other]
- If "Fail" or "Other", ask for details before continuing
- Always test from `/tmp` to avoid polluting the working directory

## Skill Activation

This skill activates when user types "qa-local" or asks for QA steps. It should be discoverable via `skills/index.json`.