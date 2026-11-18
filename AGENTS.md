# Agent Guidance

## Purpose

Give agents concise, practical rules for making verified progress in this repository.

## Core Principles

- Prefer the smallest complete change; avoid unrelated edits and unnecessary context.
- Use repository guidance first and verify assumptions against the current files.
- Take an action or produce an artifact after analysis; do not repeat reasoning without new evidence.
- Follow applicable safety, privacy, and repository constraints.

## Agent Loop

For each task:

1. **Understand Goal** — identify the requested outcome and constraints.
2. **Assess Current State** — consult `WORK_STATE`, then inspect relevant files and existing validation.
3. **Create Next Smallest Action** — choose one concrete step that advances the goal.
4. **Execute** — make the focused change or investigation.
5. **Verify Result** — run relevant checks and inspect the resulting diff.
6. **Record Findings** — capture reusable knowledge and, if unfinished, update `WORK_STATE`.
7. **Decide** — continue, hand off to another iteration, or complete.

## Autonomous Learning

After each completed task, briefly consider what worked, what failed or caused delay, and what reusable knowledge was found. Record only durable, actionable lessons; do not preserve one-off task details as general guidance.

## Skills Management

- Promote a discovered procedure to a `SKILLS` entry only when it is generic, reusable, and actionable.
- Keep each skill concise and focused on a repeatable workflow; omit one-off findings.
- Before adding a skill, check whether existing guidance already covers it.

## Work State Management

Consult this `WORK_STATE` section before new reasoning. For work that may continue in another iteration, replace the placeholders with verified task-specific facts before ending. Keep the state concise and clear it when the task is complete.

### WORK_STATE

- **Objective:** None (no active handoff)
- **Current Status:** Not in progress
- **Completed Work:** N/A
- **Verified Facts:** N/A
- **Open Questions:** N/A
- **Failed Attempts:** N/A
- **Next Actions:** N/A
- **Recommended Entry Point:** N/A
- **Known Risks / Confidence:** N/A

## Continuation Rules

- Update `WORK_STATE` before handing off unfinished work. Include exact progress, partial work, blockers, next investigation path, remaining tasks, known risks, and confidence.
- If progress stalls, recognize repeated reasoning, circular plans, or tool calls that add no evidence. After multiple unproductive attempts, record the blocker and next action, then hand off rather than looping.
- Resume from `WORK_STATE`; do not make a future iteration rediscover verified facts.
- When available, use tool-driven continuation for unfinished work; do not signal termination while objectives remain unresolved.

## Completion Rules

Complete only when the objective is satisfied, outcomes are verified, and no known critical blockers remain. Otherwise continue the loop or provide a handoff. On completion, record reusable lessons and reset `WORK_STATE` to its inactive placeholders.

## Knowledge Hierarchy

Resolve conflicts in this order:

1. `WORK_STATE`
2. `SKILLS`
3. Repository documentation
4. Source code
5. External knowledge
