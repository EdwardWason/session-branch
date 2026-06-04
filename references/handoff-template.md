# Session Handoff Document Template

> This template defines the structure for a project handoff document.
> When generating a handoff, fill in each section with project-specific content.
> **Never include personal information** — use placeholders for names, paths, and credentials.

---

## 1. Project Identity

| Field | Value |
|-------|-------|
| Project name | `<project-name>` |
| One-line description | `<description>` |
| GitHub | `https://github.com/<owner>/<repo>` |
| ClawHub slug | `<slug>` (if applicable) |
| Current version | `<X.Y.Z>` |
| Project directory | `<absolute-path-to-project>` |
| Tech stack | `<language> / <framework> / <tools>` |
| License | `<license-type>` |

---

## 2. Decision Chain (Why This Approach)

| Decision | Chosen | Rejected alternatives | Reason |
|----------|--------|----------------------|--------|
| `<decision-1>` | `<chosen>` | `<rejected>` | `<why>` |
| `<decision-2>` | `<chosen>` | `<rejected>` | `<why>` |

---

## 3. Data Flow & Execution Pipeline

```
┌──────────┐    ┌──────────┐    ┌──────────┐
│ Step 1    │ →  │ Step 2    │ →  │ Step 3    │
│ <name>    │    │ <name>    │    │ <name>    │
│ <input>   │    │ <process> │    │ <output>  │
└──────────┘    └──────────┘    └──────────┘
```

**Data format flow**:
- `<step-1>` → `<output-file-format>`
- `<step-2>` → `<output-file-format>`
- `<step-3>` → `<output-format>`

**Trigger modes**:
- Interactive: `<how>`
- Cron/Scheduled: `<how>`

---

## 4. Capability Boundary

### Can Do
- `<capability-1>`
- `<capability-2>`

### Cannot Do (Current Limitations)
- `<limitation-1>`
- `<limitation-2>`

### Dependency Constraints
| Dependency | Constraint | Impact |
|------------|-----------|--------|
| `<dep-1>` | `<constraint>` | `<impact>` |
| `<dep-2>` | `<constraint>` | `<impact>` |

---

## 5. Project File Structure

```
<project-name>/
├── <file-1>                  # <description>
├── <file-2>                  # <description>
├── <dir-1>/
│   └── <file>                # <description>
└── <dir-2>/
    └── <file>                # <description>
```

---

## 6. Platform Status

### GitHub Repository
- Repo: `<owner>/<repo>`
- Release: `<version>` (<status>)
- File count: `<N>`

### ClawHub (if applicable)
| Version | Security | Notes |
|---------|----------|-------|
| `<latest>` | CLEAN/SUSPICIOUS | `<notes>` |

---

## 7. Environment Variables

| Variable | Purpose | Status |
|----------|---------|--------|
| `<VAR_1>` | `<purpose>` | Configured / Needs user config |
| `<VAR_2>` | `<purpose>` | Configured / Needs user config |

---

## 8. Session Code Changes Summary

| File | Change | Reason |
|------|--------|--------|
| `<file-1>` | `<what changed>` | `<why>` |
| `<file-2>` | `<what changed>` | `<why>` |

---

## 9. Knowledge File Index (Load on Demand)

| Need | File to Read | Priority |
|------|-------------|----------|
| `<scenario-1>` | `<path>` | Must-read |
| `<scenario-2>` | `<path>` | On-demand |

---

## 10. User Preferences

| Preference | Description |
|-----------|-------------|
| Language | `<language>` |
| Work style | `<style>` |
| Code style | `<style>` |
| Security sensitivity | `<level>` |

---

## 11. Branchable Directions

| # | Direction | Files Involved | Prerequisites | Complexity |
|---|-----------|---------------|---------------|------------|
| A | `<direction-1>` | `<files>` | `<prereqs>` | Low/Med/High |
| B | `<direction-2>` | `<files>` | `<prereqs>` | Low/Med/High |

---

## 12. Startup Prompt for New Session

(Generated from `references/startup-prompts.md` based on target IDE)
