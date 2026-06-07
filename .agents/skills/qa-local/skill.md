# QA Local Skill

Use this skill when the user wants QA steps for testing agent-init locally.

## Skill Definition

**Name**: qa-local
**Trigger**: User invokes "qa-local" or asks for QA steps
**Purpose**: Provide exact, step-by-step QA testing instructions

## QA Steps

### Prerequisites
```bash
npm link
```

### Test 1: Create New Project
```bash
cd /tmp
rm -rf test-agent-project
agent-init
```
**When prompted:**
- Project name: `test-agent-project`
- What is this project about?: `A React music player`
- Author name: `Test User`

**Verify:**
- [ ] Project directory created at `/tmp/test-agent-project`
- [ ] `README.md` contains "A React music player"
- [ ] `AGENTS.md` exists
- [ ] `worklog.md` exists
- [ ] `.agents/config/primary.json` exists
- [ ] `.agents/prompts/system.md` exists

### Test 2: Create Project with Default Values
```bash
cd /tmp
rm -rf my-agent-project
agent-init
```
**When prompted:** Press Enter for all defaults

**Verify:**
- [ ] Project created at `/tmp/my-agent-project`
- [ ] Default description "General purpose agent-ready project" in files
- [ ] Author defaults to system username

### Test 3: Overwrite Existing Directory
```bash
cd /tmp
agent-init
```
- Enter project name: `test-agent-project`
- When asked to overwrite: answer `No`
- Verify it exits gracefully with "Aborted."
- Then run again and answer `Yes`
- Verify files are created in existing directory

### Test 4: Project About Field
```bash
cd /tmp
rm -rf project-with-desc
agent-init
```
- Project name: `project-with-desc`
- What is this project about?: `Backend API for task management`
- Author: `Dev`

**Verify:**
- [ ] `README.md` contains "Backend API for task management"
- [ ] `.agents/prompts/system.md` contains "Backend API for task management"
- [ ] `worklog.md` contains "Backend API for task management"

## Cleanup
```bash
rm -rf /tmp/test-agent-project /tmp/my-agent-project /tmp/project-with-desc
```

## Notes

- Always test from `/tmp` to avoid polluting the working directory
- Clean up test projects after verification
- Report any deviations from expected behavior