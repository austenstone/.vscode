---
description: IMPORTANT: Parallel work
# applyTo: 'IMPORTANT: Parallel work' # when provided, instructions will automatically be added to the request context when the pattern matches an attached file
---

# Parallel Work & Subagents

## Core Rule
**Always invoke multiple `runSubagent` tool calls in a SINGLE message block** when tasks are independent. Never sequentially chain what can be parallelized.

## When to Use Subagents
- Research, codebase exploration, multi-file analysis, code review, and any isolated subtask that doesn't depend on another's output.
- When a task touches N independent files/modules → spawn N parallel subagents, one per file.
- For read-only exploration, prefer the `Explore` agent — it's optimized for fast codebase Q&A.

## Orchestrator Discipline
- **The main conversation is a thin coordinator** — it delegates, synthesizes, and decides. Subagents eat the token budget for exploration and implementation.
- **Context isolation is the point.** Subagents keep verbose output (searches, logs, test runs) out of the main thread, preventing context poisoning.
- Give each subagent a focused prompt with explicit output format and length. Vague prompts = bloated returns = burned orchestrator context.
- Have each subagent write to a distinct file when possible — creates an audit trail and makes synthesis debuggable.

## Patterns
- **Scatter-gather:** N independent tasks → N parallel subagents → synthesize results.
- **Assembly line:** Chain sequentially — engineer writes → reviewer critiques → engineer fixes → re-review. Loop until approved.
- **Plan-implement-review:** Break complex tasks into phases, each handled by a separate subagent.

## Constraints
- **Concurrency:** Sweet spot 3–10. Hard ceiling ~40 before rate limiting.
- **Flat hierarchy:** Subagents cannot spawn their own subagents.
- **Reads parallel, writes partitioned:** Multiple subagents reading different files = safe. Editing the same file = conflicts. Partition writes by file.
- **Return budget:** Every subagent return lands in main context. 10 verbose returns = blown context window.
- **Failure is cheap:** If a subagent botches it, fire again. Optimize for speed and volume over per-attempt perfection.

Ref: [VS Code Subagents Docs](https://code.visualstudio.com/docs/copilot/agents/subagents)
