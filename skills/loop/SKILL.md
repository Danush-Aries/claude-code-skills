---
name: loop
description: Repeatedly run a task until a condition is met, a target count is reached, or you decide to stop. Use for iterative improvement, test-fix cycles, polling, or "keep trying until it works". Triggers on "loop", "keep running", "repeat until", "iterate", "try until passing".
argument-hint: "[task] [--until condition] [--max N] [--interval seconds]"
arguments: [task, until, max, interval]
allowed-tools:
  - Read
  - Bash
  - Grep
  - Glob
  - Edit
  - Write
---

# Loop

**Task:** `$task`
**Stop condition:** `$until` (default: user says stop or max iterations)
**Max iterations:** `$max` (default: 10 — safety cap)
**Interval:** `$interval` seconds between iterations (default: 0)

## Execution

Run `$task` repeatedly:

**Iteration 1:**
- Execute the task
- Check stop condition: `$until`
- Report result: ✅ success / ❌ failed / ⏳ in progress
- Decide: continue or stop?

**Iteration 2, 3, ... N:**
- Same cycle
- Show delta from previous iteration (what changed?)
- Stop if: condition met, max reached, or 3 consecutive identical results (stuck detector)

## Stop conditions

The loop stops when ANY of these are true:
1. `$until` condition evaluates to true
2. Max iterations (`$max`) reached
3. Three consecutive iterations with identical output (stuck)
4. An iteration throws an unrecoverable error
5. User interrupts (Esc)

## Output per iteration

```
[Iteration N/max] Task result
Condition check: PASS/FAIL
Delta from last: [what changed]
```

## Final summary

```
Loop complete after N iterations
Condition met: YES/NO
Final state: [description]
```
