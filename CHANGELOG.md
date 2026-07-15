# Changelog

All notable changes to session-branch will be documented in this file.

## [1.3.0] - 2026-06-12

### Added
- Trae IDE session-copy architecture fusion: 8-section fixed structure with token budget management (~4000 tokens)
- Compression strategy with P0-P3 priority levels (P0: user messages + current work; P3: conversation language)
- TRAE memory system integration: 3-layer memory reference (user profile, project memory, recent topics)
- New reference file: `references/memory-guide.md` — TRAE memory system path structure + quick lookup guide
- TRAE SOLO startup prompt enhanced: 4-layer context loading (handoff doc + rules + memory system + session_memory grep)
- All IDE startup prompts now include "unfinished Todos" reporting in Step 2
- Checklist updated with token budget verification section

### Changed
- handoff-template.md: restructured from 13 dimensions to 8 core sections + supplementary context
- checklist.md: restructured from 13 categories (A-M) to 8 core (A-H) + supplementary (I-N) + IDE-specific (O-P)
- Step 1 scanning list aligned with 8-section structure
- SKILL.md: new Step 1.5 (Apply Compression Strategy) added between scanning and document generation

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
