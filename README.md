# Session Branch

[![version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/EdwardWason/session-branch)
[![License](https://img.shields.io/badge/license-MIT--0-green)](LICENSE)
[![ClawHub](https://img.shields.io/badge/ClawHub-session--branch-orange)](https://clawhub.ai/skills/session-branch)

Branch your current coding session into a new conversation without losing context. Generate a structured handoff document, startup prompts, and guide the new session to pick up exactly where you left off.

## Why

When a coding conversation gets long, LLM context compression degrades quality. You want to start fresh but keep all the knowledge, decisions, and code context. Session Branch solves this by generating a comprehensive handoff document that a new AI session can read to "hot start" your project.

## Features

- **Structured Handoff Document** — 12-section template covering project identity, decision chain, data flow, capability boundary, code changes, platform status, and more
- **Validation Checklist** — 12 categories, 40+ items to ensure nothing is missed
- **IDE-Specific Startup Prompts** — Pre-built templates for TRAE SOLO, WorkBuddy, Cursor, and Claude Code
- **Three-Step Startup Flow** — Load → Report → Ask, so the new AI understands before acting
- **Personal Info Auto-Filter** — Strips real names, paths, tokens, and secrets from handoff docs
- **Branchable Directions** — Enumerates what can be built next with prerequisites and complexity

## Quick Start

### ClawHub Install

```
clawhub install session-branch
```

### Usage

In your current conversation, say:

- "开个支线" / "分叉" / "branch" / "新任务但保留上下文"

The skill will:
1. Analyze your current session and project
2. Generate a `docs/session-handoff.md` in your project
3. Give you a startup prompt for the new conversation

### In the New Conversation

Paste the startup prompt. The new AI will:
1. Read the handoff document + rules
2. Report what it learned
3. Suggest branchable directions
4. Ask you which direction to pursue

## Configuration

| Setting | Default | Description |
|---------|---------|-------------|
| `handoff_path` | `docs/session-handoff.md` | Where to save the handoff document |
| `include_checklist` | `true` | Whether to validate against checklist |
| `target_ide` | `auto` | Target IDE for startup prompt (auto/trae/workbuddy/cursor/claude-code) |

## Documentation

| Document | Description |
|----------|-------------|
| [SKILL.md](SKILL.md) | Skill specification and execution flow |
| [handoff-template.md](references/handoff-template.md) | Full template for handoff documents |
| [checklist.md](references/checklist.md) | Validation checklist (12 categories) |
| [startup-prompts.md](references/startup-prompts.md) | IDE-specific startup prompt templates |
| [CHANGELOG.md](CHANGELOG.md) | Version history |

## License

MIT-0

---

# Session Branch

[![version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/EdwardWason/session-branch)
[![License](https://img.shields.io/badge/license-MIT--0-green)](LICENSE)

Branch your current coding session into a new conversation with full context handoff.

## Why

Long conversations suffer from context compression. Session Branch generates a structured handoff document so a new AI session can hot-start your project.

## Features

- 12-section structured handoff template
- 40+ item validation checklist
- IDE-specific startup prompts (TRAE SOLO / WorkBuddy / Cursor / Claude Code)
- Three-step startup flow: Load → Report → Ask
- Personal information auto-filtering
- Branchable directions with prerequisites

## Quick Start

```
clawhub install session-branch
```

Then say "branch" or "开个支线" in your conversation.

## Documentation

| Document | Description |
|----------|-------------|
| [SKILL.md](SKILL.md) | Skill specification |
| [handoff-template.md](references/handoff-template.md) | Handoff document template |
| [checklist.md](references/checklist.md) | Validation checklist |
| [startup-prompts.md](references/startup-prompts.md) | Startup prompt templates |

## License

MIT-0
