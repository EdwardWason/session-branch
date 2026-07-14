# Changelog

All notable changes to session-branch will be documented in this file.

## [1.2.0] - 2026-06-12

### Security
- Added Privacy & Consent section: file write warning, consent gate for IDE-specific scanning, env var value harvesting prohibition, project-relative paths only
- IDE-specific file scanning (WorkBuddy identity/memory/skills/tasks/channels/MCP) now requires explicit user consent before execution
- Environment variable scanning now records only variable names and configured status (yes/no), never values
- Fixed path contradiction: startup prompts and handoff template now use project-relative paths exclusively, never absolute paths containing usernames
- Checklist updated: added env var value check, consent verification, and absolute path prohibition

### Changed
- Trigger words updated to: "支线任务" / "开个支线" / "分叉" (removed generic "branch" and "新任务但保留上下文")
- README: added filesystem modification warning and consent notice in both Chinese and English sections

## [1.1.0] - 2026-06-04

### Added
- WorkBuddy deep adaptation: identity files (SOUL.md/IDENTITY.md/USER.md), memory system (MEMORY.md + daily logs), installed skills, scheduled tasks, IMA/Feishu channel config, MCP connectors
- IDE-specific additional scanning in SKILL.md Step 1 (WorkBuddy/TRAE SOLO/Cursor/Claude Code)
- Handoff document save location varies by IDE (`.workbuddy/` for WorkBuddy, `docs/` for others)
- Handoff template section 13: IDE-Specific Context with WorkBuddy identity/memory/skills/tasks/channels/MCP
- Checklist section M: IDE-Specific Checks (WorkBuddy 7 items, TRAE SOLO 3 items, Cursor 2 items, Claude Code 2 items)
- Branchable directions now tagged by type (Research / Engineering / Ops)
- Startup prompt for WorkBuddy now loads SOUL.md and MEMORY.md, uses `.workbuddy/session-handoff.md` path

## [1.0.0] - 2026-06-04

### Added
- Initial release
- Structured handoff document generation (12-section template)
- Validation checklist (12 categories, 40+ items)
- IDE-specific startup prompts (TRAE SOLO / WorkBuddy / Cursor / Claude Code)
- Three-step startup flow: Load → Report → Ask
- Personal information auto-filtering
- Capability boundary analysis (can/cannot/constraints)
- Branchable directions enumeration with prerequisites
