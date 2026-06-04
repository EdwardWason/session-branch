# Handoff Document Generation Checklist

When generating a handoff document, verify every item is covered.
If an item is not applicable, write "N/A" with a reason.

---

## A. Project Identity
- [ ] Project name and one-line description
- [ ] Platform URLs (GitHub, ClawHub, npm, PyPI, etc.)
- [ ] Current version number
- [ ] Project directory absolute path
- [ ] Tech stack
- [ ] License

## B. Decision Chain
- [ ] Each key technical decision: what was chosen, what was rejected, why
- [ ] Naming strategy (cross-platform slug mapping if applicable)
- [ ] Architecture choices with rationale

## C. Data Flow & Execution Pipeline
- [ ] End-to-end execution flow diagram
- [ ] Data format flow (input → processing → output)
- [ ] Trigger modes (Interactive / Cron / Manual)

## D. Capability Boundary
- [ ] What the project CAN do (current capabilities)
- [ ] What the project CANNOT do (current limitations)
- [ ] Dependency constraints (external APIs, platforms, toolchain limits)

## E. Code Changes
- [ ] Which files were modified in this session
- [ ] Why each modification was made
- [ ] Current code state (committed / uncommitted)

## F. Platform Status
- [ ] GitHub repository file count, Release status
- [ ] ClawHub version, Security status (if applicable)
- [ ] Other platforms (npm, PyPI, Docker Hub, etc.)

## G. Environment Variables
- [ ] Which env vars are configured
- [ ] Which need user configuration
- [ ] Token types and required permissions

## H. Knowledge File Index
- [ ] Indexed by scenario (not by filename)
- [ ] Priority annotated (Must-read / On-demand)
- [ ] Full index file location

## I. User Preferences
- [ ] Communication language
- [ ] Work style
- [ ] Code style
- [ ] Security sensitivity level

## J. Branchable Directions
- [ ] Each direction lists files involved
- [ ] Prerequisites for each direction
- [ ] Complexity estimate (Low / Medium / High)

## K. Pending Items
- [ ] Unfinished tasks
- [ ] Known issues
- [ ] Improvement ideas

## L. Startup Prompt
- [ ] Three-step flow: Load → Report → Ask
- [ ] Adapted for target IDE platform
- [ ] Role set: "continuation of existing project, not starting from scratch"
- [ ] Exact file paths included (absolute paths)

---

## Personal Information Filter

Before finalizing the handoff, scan and remove:

- [ ] No real names (use `<owner>` or `<contributor>`)
- [ ] No real email addresses
- [ ] No absolute paths containing usernames (use `<project-dir>`)
- [ ] No token values (use `<your-token>`)
- [ ] No internal network addresses or VPN endpoints
- [ ] No project-specific secrets or API keys
- [ ] No personal preferences that are project-specific (keep generic patterns)
