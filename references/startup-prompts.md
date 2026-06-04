# Startup Prompt Templates

Templates for the new conversation's opening prompt, adapted per IDE.

---

## Universal Template (All IDEs)

```
This is a continuation of an existing project. Follow these steps:

Step 1: Load context
1. Read `<project-dir>/docs/session-handoff.md` (project handoff document)
2. Read `<project-dir>/docs/rules/coding-standards.md` (coding standards)
3. Read `<project-dir>/docs/rules/processes.md` (process rules)

Step 2: Report to me
- What files you read and what you learned about the project
- Your understanding of the task I want to do
- Based on the project's current state and my task, what branchable directions are feasible

Step 3: Ask me
- Which direction I want to pursue
- Any technical details you're unsure about and need me to confirm

My task is: <TASK_DESCRIPTION>
```

---

## TRAE SOLO

Same as Universal Template. TRAE SOLO supports absolute paths natively.

Additional note for TRAE SOLO:
- Rules in `.trae/rules/` are auto-loaded — no need to mention them in the prompt
- The `docs/knowledge/` directory contains deep knowledge files — load on demand, not upfront

---

## WorkBuddy (Tencent)

```
这是一个已有项目的支线任务。请按以下步骤启动：

第一步：加载上下文
1. 读取项目目录下的 `docs/session-handoff.md`（项目交接文档）
2. 读取 `docs/rules/coding-standards.md`（编码规范）
3. 读取 `docs/rules/processes.md`（流程规范）

第二步：向我汇报
- 你读取了哪些文件，了解到项目的什么状态
- 你对我要做的任务有什么理解
- 基于项目当前状态和我的任务，有哪些可行的支线方向

第三步：问我
- 在你建议的方向中，我想走哪一条
- 有没有你不确定的技术细节需要我确认

我的任务是：<任务描述>
```

Note: WorkBuddy prefers Chinese prompts. Use relative paths if absolute paths are not supported.

---

## Cursor

Same as Universal Template. Cursor supports absolute paths.

Additional note:
- Cursor's `.cursor/rules/` is auto-loaded — equivalent to TRAE's `.trae/rules/`
- If the project has `.cursorrules`, mention it in the handoff doc

---

## Claude Code

```
This is a continuation of an existing project. Follow these steps:

Step 1: Load context
1. Read the file `docs/session-handoff.md` in the project root
2. Read `docs/rules/coding-standards.md`
3. Read `docs/rules/processes.md`

Step 2: Report to me
- What you read and what you learned about the project state
- Your understanding of the task
- What directions are feasible given the current state

Step 3: Ask me
- Which direction I want to pursue
- Any technical details you need confirmed

My task is: <TASK_DESCRIPTION>
```

Note: Claude Code uses `CLAUDE.md` for project-level rules. If the project has one, mention it in the handoff doc.

---

## Customization Guide

To adapt for a new IDE:

1. Check if the IDE auto-loads rules files (if yes, don't include them in the prompt)
2. Check if the IDE supports absolute paths (if not, use relative paths)
3. Check the IDE's preferred language (Chinese IDEs may prefer Chinese prompts)
4. Add the new template to this file and update SKILL.md's `target_ide` config
