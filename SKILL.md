---
name: "session-branch"
description: "Branch a coding session into a new conversation with full context handoff — generate structured handoff doc and startup prompts. Do NOT use for new projects, general coding, or non-handoff session management."
version: "1.2.0"
slug: "session-branch"
displayName: "Session Branch"
summary: "将当前编码会话分叉到新对话，完整保留上下文。自动生成结构化交接文档和启动提示词。"
license: "MIT-0"
tags: ["session", "handoff", "branch", "context", "continuity"]
---

# Session Branch

Branch your current coding session into a new conversation without losing context.

## When to Use

- Current conversation is getting long and context compression is degrading quality
- You want to start a new task on the same project but keep full context
- You need to fork your work into a parallel direction
- User says: "支线任务" / "开个支线" / "分叉"

## Privacy & Consent

**Before executing any step, the agent MUST:**

1. **Warn the user** that this skill will write a file to the project directory (e.g., `docs/session-handoff.md`)
2. **Ask for explicit consent** before scanning any IDE-specific identity, memory, or configuration files
3. **Never harvest env var values** — only record variable names and whether they are configured (yes/no)
4. **Use project-relative paths** in all generated documents — never absolute paths containing usernames or home directories

## Execution Flow

### Step 1: Analyze Current Session

Scan the current conversation and project to extract:

1. **Project identity** — name, description, platforms, version, tech stack
2. **Decision chain** — what was chosen, what was rejected, and why
3. **Data flow** — how data moves through the system (input → process → output)
4. **Capability boundary** — what the project CAN do and CANNOT do
5. **Code changes** — what files were modified in this session and why
6. **Platform status** — GitHub, ClawHub, npm, PyPI current state
7. **Environment** — which env var names are configured (yes/no status only, never harvest values)
8. **Knowledge files** — index of docs/knowledge/ and docs/rules/ by scenario
9. **User preferences** — language, work style, code style, security sensitivity
10. **Branchable directions** — what can be built next, with files involved and prerequisites

#### IDE-Specific Additional Scanning

> **Consent required**: Before scanning any of the following, inform the user what files will be accessed and ask for explicit permission. Skip any category the user declines.

**For WorkBuddy**, also scan (with user consent):
- **Identity files**: `~/.workbuddy/SOUL.md`, `IDENTITY.md`, `USER.md` — persona and preferences
- **Memory files**: `.workbuddy/memory/MEMORY.md` + daily logs — project memory
- **Installed skills**: `~/.workbuddy/skills/` — list of active skills
- **Scheduled tasks**: automation/cron task list and status
- **Channel config**: IMA knowledge base IDs, Feishu channel configuration
- **MCP connectors**: active MCP connector status

**For TRAE SOLO**, also scan:
- **Rules**: `.trae/rules/` — project-level rules
- **Schedule**: TRAE SOLO Schedule task list

**For Cursor**, also scan:
- **Rules**: `.cursor/rules/` or `.cursorrules`

**For Claude Code**, also scan:
- **Rules**: `CLAUDE.md` in project root

### Step 2: Generate Handoff Document

Use the template at `references/handoff-template.md` to create a structured handoff document.

**Save location by IDE**:

| IDE | Default path | Rationale |
|-----|-------------|-----------|
| WorkBuddy | `.workbuddy/session-handoff.md` | Align with memory system, keep project root clean |
| TRAE SOLO | `docs/session-handoff.md` | Standard docs location |
| Cursor | `docs/session-handoff.md` | Standard docs location |
| Claude Code | `docs/session-handoff.md` | Standard docs location |

**Critical rules**:
- NO personal information (real names, emails, token values)
- NO project-specific secrets or credentials
- Use project-relative paths (e.g., `docs/session-handoff.md`), never absolute paths containing usernames or home directories
- Use generic placeholders: `<project-name>`, `<owner>`, `<your-path>`
- The handoff doc must be reusable as a TEMPLATE, not a one-time snapshot

### Step 3: Validate with Checklist

Cross-check the generated handoff against `references/checklist.md`.

Every item must be covered. If something is not applicable, write "N/A" with a reason.

### Step 4: Generate Startup Prompt

Use `references/startup-prompts.md` to generate the startup prompt for the new conversation.

The prompt must include:
1. Project-relative file paths for the new AI to read (never absolute paths with usernames)
2. A three-step flow: Load → Report → Ask
3. Clear role: "This is a continuation of an existing project, not starting from scratch"

### Step 5: Present to User

Show the user:
1. The generated handoff document (key sections summary)
2. The startup prompt (ready to copy-paste)
3. List of files created and their locations
4. Ask: "Ready to open a new conversation?"

## Permission Declaration

| Capability | Used | Description |
|------------|------|-------------|
| Network | No | No network access required |
| File read/write | Yes | Reads project files; writes `docs/session-handoff.md` (overwrites if exists) |
| Environment variables | Yes | Reads env var names (status only, never values) |
| subprocess | No | No subprocess calls |
| External API | No | No external API calls |

## Configuration

| Setting | Default | Description |
|---------|---------|-------------|
| `handoff_path` | Auto (by IDE) | Where to save the handoff document |
| `include_checklist` | `true` | Whether to validate against checklist |
| `target_ide` | `auto` | Target IDE for startup prompt (auto/trae/workbuddy/cursor/claude-code) |

## References

- `references/handoff-template.md` — Full template for the handoff document
- `references/checklist.md` — Validation checklist (12 categories + IDE-specific)
- `references/startup-prompts.md` — IDE-specific startup prompt templates
