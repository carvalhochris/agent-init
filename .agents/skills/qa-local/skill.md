# QA Local Skill

Use this skill when the user wants QA steps for testing agent-init locally.

## Skill Definition

**Name**: qa-local
**Trigger**: User invokes "qa-local" or asks for QA steps
**Purpose**: Provide exact, step-by-step QA testing instructions

## QA Steps (One at a time)

### Step 1: Build and Link
```bash
npm run build && npm link
```
**Wait for completion, then ask:** Pass, fail, or other?

### Step 2: Create New Project
```bash
cd /tmp && rm -rf test-agent-project && agent-init
```
**When prompted:**
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

**Wait for verification, then ask:** Pass, fail, or other?

### Step 3: Create Project with Defaults
```bash
cd /tmp && rm -rf my-agent-project && agent-init
```
Press Enter for all defaults.

**Verify:**
- Project created at `/tmp/my-agent-project`
- Default description "General purpose agent-ready project" in files
- Author defaults to system username

**Wait for verification, then ask:** Pass, fail, or other?

### Step 4: Overwrite Existing Directory
```bash
cd /tmp && agent-init
```
- Enter project name: `test-agent-project`
- When asked to overwrite: answer `No`
- Verify it exits gracefully with "Aborted."

**Wait for verification, then ask:** Pass, fail, or other?

### Step 5: Continue Overwrite
```bash
cd /tmp && agent-init
```
- Enter project name: `test-agent-project`
- When asked to overwrite: answer `Yes`
- Verify files are created in existing directory

**Wait for verification, then ask:** Pass, fail, or other?

### Step 6: Project About Field
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

**Wait for verification, then ask:** Pass, fail, or other?

### Step 7: Cleanup
```bash
rm -rf /tmp/test-agent-project /tmp/my-agent-project /tmp/project-with-desc
```
**Wait for completion, then ask:** Pass, fail, or other?

## Notes

- Give one step at a time
- After each step, ask "Pass, fail, or other?"
- If "fail" or "other", get details before continuing
- Always test from `/tmp` to avoid polluting the working directory