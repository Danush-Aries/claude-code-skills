---
name: batch
description: Execute the same task across multiple files, items, or targets in parallel using subagents. Use for bulk operations like "refactor all these files", "add tests to every module", "rename X to Y across the codebase". Triggers on "batch", "all files", "across the codebase", "every module", "bulk".
argument-hint: "[task-description] [--pattern glob] [--max-agents N]"
arguments: [task, pattern, max_agents]
allowed-tools:
  - Read
  - Glob
  - Grep
  - Bash(find *)
  - Agent
context: fork
agent: general-purpose
---

# Batch Operation

**Task:** `$task`
**File pattern:** `$pattern` (default: auto-detect from task)
**Max parallel agents:** `$max_agents` (default: 5)

## Step 1 — Discover targets

Find all files/items matching the pattern:

```!
echo "Discovering targets..."
```

If `$pattern` is empty, infer from `$task`:
- "add tests" → `**/*.py` or `**/*.ts` source files
- "refactor X" → files containing X
- "update imports" → all source files

List the targets. If more than 20, ask for confirmation before proceeding.

## Step 2 — Plan the operation

For each target, describe what will change. Show a sample diff for 1-2 items before doing all of them.

**Stop here and confirm** if the task involves destructive changes (deletes, overwrites).

## Step 3 — Execute in parallel

Spawn up to `$max_agents` (default: 5) subagents, each handling a slice of the targets:

For each subagent:
- Give it a specific list of files
- Same task description
- Isolated context (no shared state)

## Step 4 — Collect and verify results

After all subagents complete:
- Count successes vs failures
- Show what changed (summary diff)
- List any files that failed and why
- Confirm no unintended side effects

## Output

```
Batch complete: N/M targets processed
✅ Success: [list]
❌ Failed: [list with reasons]
```
