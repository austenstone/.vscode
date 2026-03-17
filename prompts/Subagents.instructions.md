---
description: IMPORTANT: Parallel work
# applyTo: 'IMPORTANT: Parallel work' # when provided, instructions will automatically be added to the request context when the pattern matches an attached file
---

# Parallel Work & Subagents

## Core Rule
**Always invoke multiple `runSubagent` tool calls in a SINGLE message block** when tasks are independent. Never sequentially chain what can be parallelized. **Default to 5+ parallel subagents** when the task allows it.

## Agent Selection
- **Default (unnamed) subagent** is the workhorse. It inherits ALL parent tools — MCP, terminal, file editing, everything. **Use this for any task that needs to take action** (GitHub API calls, file edits, code fixes, running commands).
- **`Explore` agent** is read-only and tool-restricted. ONLY use it for pure codebase Q&A where no MCP tools, terminal, or writes are needed.
- **When in doubt, use default.** A default subagent can do everything Explore can, plus more. The only cost is slightly more tool surface.

## When to Use Subagents
- ANY task that can be decomposed into 2+ independent pieces — parallelize immediately.
- Research, codebase exploration, multi-file analysis, code review, GitHub API operations, CI/CD fixes, PR management.
- When a task touches N independent repos/files/modules → spawn N parallel subagents, one per target.
- **Bias hard toward parallelism.** If you're debating whether to parallelize, parallelize.

## Orchestrator Discipline
- **The main conversation is a thin coordinator** — it delegates, synthesizes, and decides. Subagents eat the token budget for exploration and implementation.
- **Context isolation is the point.** Subagents keep verbose output (searches, logs, test runs) out of the main thread, preventing context poisoning.
- Give each subagent a focused prompt with explicit output format and length. Vague prompts = bloated returns = burned orchestrator context.
- Tell subagents exactly which tools to use (e.g. "use mcp_github-mcp-se_create_or_update_file to push the fix").
- Have each subagent write to a distinct file when possible — creates an audit trail and makes synthesis debuggable.

## Patterns
- **Scatter-gather:** N independent tasks → N parallel subagents → synthesize results.
- **Assembly line:** Chain sequentially — engineer writes → reviewer critiques → engineer fixes → re-review. Loop until approved.
- **Plan-implement-review:** Break complex tasks into phases, each handled by a separate subagent.
- **Fan-out fix:** Multiple repos need the same type of fix → one subagent per repo, all in parallel.

## Constraints
- **Concurrency:** Sweet spot 5–10. Hard ceiling ~40 before rate limiting.
- **Flat hierarchy:** Subagents cannot spawn their own subagents.
- **Reads parallel, writes partitioned:** Multiple subagents reading different files = safe. Editing the same file = conflicts. Partition writes by file/repo.
- **Return budget:** Every subagent return lands in main context. Cap returns to essential info only — tell subagents to be concise.
- **Failure is cheap:** If a subagent botches it, fire again. Optimize for speed and volume over per-attempt perfection.

Ref: [VS Code Subagents Docs](https://code.visualstudio.com/docs/copilot/agents/subagents)
