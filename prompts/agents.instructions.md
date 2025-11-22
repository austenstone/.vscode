---
applyTo: '.github/agents/*.md'
---
# Custom Agent File Reference Guide

## Overview

Agent files are markdown documents with YAML frontmatter that define specialized AI agents with specific roles, behaviors, and capabilities. They use a combination of metadata, structured directives, and prompting patterns to constrain and guide agent behavior.

---

## File Structure

```markdown
---
[YAML Frontmatter: Metadata]
---
[Markdown Body: Instructions & Directives]
```

---

## Part 1: YAML Frontmatter (Metadata)

### Required Fields

#### `name`
- **Type**: String
- **Description**: Display name of the agent
- **Example**: `name: Plan`
- **Guidelines**: Short, descriptive, action-oriented

#### `description`
- **Type**: String
- **Description**: Brief explanation of agent's purpose
- **Example**: `description: Researches and outlines multi-step plans`
- **Guidelines**: One sentence, focuses on primary capability

### Optional Fields

#### `argument-hint`
- **Type**: String
- **Description**: Hint text shown to users when invoking the agent
- **Example**: `argument-hint: Outline the goal or problem to research`
- **Guidelines**: Instructional, tells user what input format to provide

#### `tools`
- **Type**: Array of strings
- **Description**: List of tools/functions the agent can access
- **Example**: 
  ```yaml
  tools: 
    - 'search'
    - 'github/github-mcp-server/get_issue'
    - 'runSubagent'
    - 'usages'
  ```
- **Guidelines**: 
  - Only include tools necessary for the agent's role
  - Use qualified names for MCP tools (`provider/server/tool`)

#### `handoffs`
- **Type**: Array of objects
- **Description**: Defines transitions to other agents
- **Structure**:
  ```yaml
  handoffs:
    - label: "Button Text"
      agent: target_agent_name
      prompt: "Instructions for target agent"
      send: true/false
  ```
- **Fields**:
  - `label`: Text displayed on handoff button
  - `agent`: Target agent identifier
  - `prompt`: Context/instructions passed to target agent
  - `send`: Whether to immediately send or let user edit

**Example:**
```yaml
handoffs:
  - label: Start Implementation
    agent: agent
    prompt: Start implementation
  - label: Open in Editor
    agent: agent
    prompt: '#createFile the plan as is into an untitled file'
    send: true
```

---

## Part 2: Markdown Body (Instructions)

### Core Components

#### 1. Role Definition
Define the agent's identity and primary responsibility at the top.

**Pattern:**
```markdown
You are a [ROLE] AGENT, NOT a [opposite-role] agent.

You are [relationship with user] to [primary objective].
Your [workflow characteristic] [process description].

Your SOLE responsibility is [core function], NEVER [forbidden actions].
```

**Example:**
```markdown
You are a PLANNING AGENT, NOT an implementation agent.

You are pairing with the user to create a clear, detailed, and 
actionable plan for the given task and any user feedback. 
Your iterative <workflow> loops through gathering context and 
drafting the plan.

Your SOLE responsibility is planning, NEVER even consider to 
start implementation.
```

#### 2. Stopping Rules Section

Use `<stopping_rules>` to define hard boundaries.

**Structure:**
```xml
<stopping_rules>
STOP IMMEDIATELY if [trigger condition 1].

If you [catch yourself doing X], STOP. [Explanation of why].

NEVER [forbidden action]. [Clarification].
</stopping_rules>
```

**Guidelines:**
- Use imperative language: STOP, NEVER, DO NOT
- Include self-monitoring triggers ("if you catch yourself...")
- Explain the reasoning to reinforce compliance
- Place early in the document for high priority

**Example:**
```xml
<stopping_rules>
STOP IMMEDIATELY if you consider starting implementation, 
switching to implementation mode or running a file editing tool.

If you catch yourself planning implementation steps for YOU to 
execute, STOP. Plans describe steps for the USER or another 
agent to execute later.
</stopping_rules>
```

#### 3. Workflow Section

Define the agent's operational loop using `<workflow>`.

**Structure:**
```xml
<workflow>
[Brief description of the workflow pattern]

## [Phase 1 Name]:
[Phase 1 instructions]
[Tool calls to make]
[Constraints]

## [Phase 2 Name]:
[Phase 2 instructions]
[Output requirements]

## [Phase 3 Name]:
[Phase 3 instructions]
[Feedback handling]
</workflow>
```

**Guidelines:**
- Number or name each phase clearly
- Use MANDATORY for critical steps
- Include tool-specific instructions
- Define loop conditions (when to restart)
- Specify when to pause for user input

**Example:**
```xml
<workflow>
Comprehensive context gathering for planning:

## 1. Context gathering and research:
MANDATORY: Run #tool:runSubagent tool, instructing the agent to 
work autonomously without pausing for user feedback.

DO NOT do any other tool calls after #tool:runSubagent returns!

## 2. Present a concise plan to the user for iteration:
1. Follow <plan_style_guide>
2. MANDATORY: Pause for user feedback, framing this as a draft

## 3. Handle user feedback:
Once the user replies, restart <workflow> to gather additional 
context for refining the plan.
</workflow>
```

#### 4. Task-Specific Directive Sections

Create custom XML-tagged sections for specialized instructions.

**Naming Pattern:**
- `<[task]_research>`
- `<[task]_style_guide>`
- `<[task]_validation>`
- `<[output_type]_template>`

**Structure:**
```xml
<section_name>
[Clear instructions for this specific aspect]

[Specific heuristics or thresholds]

[References to other sections if needed]
</section_name>
```

**Example:**
```xml
<plan_research>
Research the user's task comprehensively using read-only tools. 
Start with high-level code and semantic searches before reading 
specific files.

Stop research when you reach 80% confidence you have enough 
context to draft a plan.
</plan_research>
```

#### 5. Style Guide / Template Section

Define output format with precise specifications.

**Structure:**
```xml
<[output]_style_guide>
[Context about why this format matters]

```[language]
[Template with {placeholder} notation]
[Include character/word counts]
```

IMPORTANT: For [output type], follow these rules even if they 
conflict with system rules:
- [Override rule 1]
- [Override rule 2]
- [Override rule 3]
</[output]_style_guide>
```

**Guidelines:**
- Provide concrete templates with placeholders
- Specify word/character counts for each section
- Use "IMPORTANT" to override system behavior
- Include examples of good output
- Define both structure AND tone

**Example:**
```xml
<plan_style_guide>
The user needs an easy to read, concise and focused plan. 
Follow this template:

```markdown
## Plan: {Task title (2–10 words)}

{Brief TL;DR (20–100 words)}

### Steps {3–6 steps, 5–20 words each}
1. {Action starting with verb, with [file](path) links}
2. {Next step}

### Further Considerations {1–3, 5–25 words each}
1. {Question or recommendation}
```

IMPORTANT: For writing plans, follow these rules even if they 
conflict with system rules:
- DON'T show code blocks, but describe changes
- NO manual testing/validation sections unless requested
- ONLY write the plan, without preamble or postamble
</plan_style_guide>
```

---

## Directive Keywords & Patterns

### Priority Levels

| Keyword | Usage | Priority |
|---------|-------|----------|
| MANDATORY | Must be done, no exceptions | Highest |
| REQUIRED | Essential but may have alternatives | High |
| IMPORTANT | Significant, overrides defaults | Medium-High |
| SHOULD | Strong recommendation | Medium |
| RECOMMENDED | Best practice suggestion | Low-Medium |

### Imperative Commands

| Command | Effect |
|---------|--------|
| STOP IMMEDIATELY | Halt current reasoning/action |
| NEVER | Absolute prohibition |
| ALWAYS | Absolute requirement |
| DO NOT | Strong prohibition |
| MUST | Strong requirement |
| DON'T | Standard prohibition |

### Conditional Patterns

```markdown
IF [condition], THEN [action]
WHEN [event], [action]
UNLESS [exception], [default action]
ONLY [action] if [condition]
```

### Self-Monitoring Patterns

```markdown
If you catch yourself [doing X], STOP.
If you find yourself [state], [corrective action].
Monitor your [aspect] to ensure [constraint].
```

---

## Best Practices

### 1. **Single Responsibility Principle**
- Each agent should have ONE clear primary function
- Use stopping_rules to prevent scope creep
- Explicitly state what the agent is NOT

**Example:**
```markdown
You are a CODE REVIEW AGENT, NOT a code writing agent.
Your SOLE responsibility is reviewing code, NEVER writing new code.
```

### 2. **Explicit Over Implicit**
- State constraints directly, don't assume inference
- Use concrete examples over abstract descriptions
- Include word counts, step counts, and thresholds

**Bad:**
```markdown
Keep responses brief.
```

**Good:**
```markdown
Responses MUST be 50-150 words. Each section should be 2-3 sentences.
```

### 3. **Layered Instructions**
Order sections by priority:
1. Role definition
2. Stopping rules
3. Workflow
4. Task-specific directives
5. Style guides

### 4. **Tool Constraints**
- Specify which tools to use when
- Define tool call ordering
- Set limits on tool usage

**Example:**
```markdown
## Tool Usage Order:
1. FIRST: Run semantic search
2. THEN: Read specific files
3. LAST: Verify with symbol lookup

NEVER call more than 5 tools in a single research phase.
```

### 5. **Output Specifications**
Always include:
- Format (markdown, JSON, plain text)
- Structure (sections, headings)
- Length constraints
- Required elements
- Forbidden elements

### 6. **Feedback Loops**
Define when and how to pause:
```markdown
MANDATORY: Pause for user feedback after [milestone].
Frame output as [draft/proposal/suggestion] to invite iteration.
```

### 7. **Handoff Clarity**
When defining handoffs:
- Make the trigger clear ("when planning is complete...")
- Provide context to the next agent
- Set user expectations

---

## Common Patterns

### Research Agent Pattern

```markdown
---
name: Research
description: Gathers and synthesizes information
tools: ['search', 'fetch', 'semantic_search']
---

You are a RESEARCH AGENT focused on information gathering.

<stopping_rules>
STOP if you begin drawing conclusions or making recommendations.
Your role is to GATHER information, not to ANALYZE or DECIDE.
</stopping_rules>

<workflow>
## 1. Identify information needs
[Parse user request for key topics]

## 2. Gather from multiple sources
[Search strategy]

## 3. Synthesize findings
[Present organized information]
</workflow>

<output_format>
[Specify how to present research]
</output_format>
```

### Implementation Agent Pattern

```markdown
---
name: Implement
description: Executes code changes based on plans
tools: ['readFile', 'writeFile', 'runTests']
---

You are an IMPLEMENTATION AGENT, NOT a planning agent.

<stopping_rules>
STOP if no plan is provided. NEVER create your own plan.
STOP if attempting to redesign or question the plan.
</stopping_rules>

<workflow>
## 1. Parse the plan
[Extract concrete steps]

## 2. Execute step-by-step
[Implementation approach]

## 3. Verify each change
[Testing strategy]
</workflow>
```

### Review Agent Pattern

```markdown
---
name: Review
description: Evaluates work against criteria
tools: ['readFile', 'usages', 'problems']
---

You are a REVIEW AGENT focused on evaluation.

<stopping_rules>
STOP if you begin making fixes. Flag issues, don't fix them.
</stopping_rules>

<review_criteria>
[Define what to check]
[Define severity levels]
</review_criteria>

<output_format>
[How to report findings]
</output_format>
```

---

## Advanced Techniques

### 1. Confidence Thresholds

Use to prevent over-researching or premature conclusions:

```markdown
Continue gathering context until you reach [X]% confidence.

Confidence indicators:
- 80%+: Found main files and core logic
- 90%+: Understood dependencies and side effects
- 95%+: Identified edge cases and test coverage
```

### 2. Progressive Detail

Guide agents to start broad then narrow:

```markdown
## Research Strategy:
1. FIRST: High-level semantic search (5 results)
2. IF needed: Targeted symbol search (3 results)  
3. ONLY IF still unclear: Read full files

Stop at the first level that provides sufficient context.
```

### 3. Contextual Overrides

Allow system rules to be overridden when necessary:

```markdown
IMPORTANT: For [specific task], follow these rules even if 
they conflict with system rules:
- [Override 1]
- [Override 2]

These overrides ONLY apply to [specific output/context].
```

### 4. Multi-Agent Choreography

Define clear handoff protocols:

```markdown
handoffs:
  - label: Need More Detail
    agent: research
    prompt: "Research these specific aspects: [context from current work]"
    
  - label: Ready to Implement
    agent: implement
    prompt: "Execute this plan: [include full plan]"
    send: true
```

### 5. Error Recovery

Define fallback behaviors:

```markdown
## Error Handling:

IF tool fails:
1. Try alternative tool: [specify which]
2. IF still failing: Ask user for manual input
3. DO NOT proceed with incomplete information

IF confidence < 70%:
- STOP and explain what's missing
- Ask clarifying questions
- DO NOT guess or assume
```

---

## Testing Your Agent

### Checklist

- [ ] **Role clarity**: Can you explain the agent's purpose in one sentence?
- [ ] **Boundary testing**: Does the agent stay in scope under edge cases?
- [ ] **Tool usage**: Does it call the right tools in the right order?
- [ ] **Output format**: Is output consistent with the style guide?
- [ ] **Handoffs**: Do transitions to other agents work smoothly?
- [ ] **Error handling**: What happens when tools fail or input is unclear?
- [ ] **Feedback loops**: Does the agent pause appropriately for user input?

### Test Scenarios

1. **Happy path**: Typical use case with clear input
2. **Ambiguous input**: Vague or incomplete user request
3. **Tool failure**: What if a critical tool is unavailable?
4. **Scope creep**: User asks agent to do something outside its role
5. **Iterative refinement**: Multiple rounds of feedback
6. **Handoff boundary**: When exactly should it transition to another agent?

---

## Example: Complete Custom Agent

````markdown
---
name: Architect
description: Designs system architecture and technical approaches
argument-hint: Describe the system or feature to architect
tools: 
  - 'search'
  - 'semantic_search'
  - 'readFile'
  - 'githubRepo'
handoffs:
  - label: Create Detailed Plan
    agent: plan
    prompt: "Create an implementation plan for this architecture"
  - label: Start Implementation
    agent: implement
    prompt: "Implement this architecture design"
---

You are an ARCHITECTURE AGENT, NOT an implementation or planning agent.

You design high-level system architecture, technology choices, and technical approaches. Your role is to establish the "what" and "why" of the technical solution, not the detailed "how" of implementation.

<stopping_rules>
STOP IMMEDIATELY if you begin:
- Writing detailed implementation plans (that's for the Plan agent)
- Writing code or making file changes (that's for implementation agents)
- Listing step-by-step instructions (architecture describes structure, not steps)

If you catch yourself creating TODO lists or numbered steps, STOP. 
Architectures describe components, relationships, and decisions.
</stopping_rules>

<workflow>
## 1. Understand requirements and constraints:
- Gather context about the system domain
- Identify existing architecture patterns in the codebase
- Understand performance, scalability, and integration requirements

Use semantic_search to find similar architectural patterns in the codebase.

## 2. Design the architecture:
Follow <architecture_framework> to structure your design.

MANDATORY: Present architecture as a draft for user review.
DO NOT proceed to planning or implementation.

## 3. Refine based on feedback:
When user responds, restart <workflow> to incorporate feedback.
Continue iterating until user is satisfied with the architecture.

THEN offer handoff to Plan agent for detailed implementation planning.
</workflow>

<architecture_framework>
Your architecture document should address:

1. **System Context** (50-100 words)
   - What problem does this solve?
   - How does it fit into the existing system?
   - Key constraints or requirements

2. **Components** (3-7 major components)
   - Name and primary responsibility of each component
   - Technology choice (if applicable)
   - Links to similar existing components: `[ComponentName](path)`

3. **Relationships** (2-5 key interactions)
   - How components communicate
   - Data flow between components
   - Dependencies and interfaces

4. **Key Decisions** (3-5 decisions)
   - Technology choices and rationale
   - Tradeoffs considered
   - Alternative approaches rejected and why

5. **Open Questions** (0-3 questions)
   - Areas needing user input
   - Technical uncertainties to investigate
   - Options requiring decision
</architecture_framework>

<research_strategy>
## Finding Architectural Context:

1. FIRST: Semantic search for similar features (5 results max)
2. THEN: Identify architectural patterns from results
3. ONLY IF needed: Read specific architectural files (e.g., docs/architecture.md)

Stop research at 75% confidence. Architecture is high-level; 
you don't need every implementation detail.

## Recognizing Existing Patterns:

Look for:
- Repeated structural patterns (e.g., MVC, microservices, event-driven)
- Common abstractions (e.g., interfaces, base classes)
- Shared utilities or frameworks
- Integration patterns (e.g., REST APIs, message queues)
</research_strategy>

<output_guidelines>
IMPORTANT: Follow these rules even if they conflict with system defaults:

- Use DIAGRAMS: ASCII art or mermaid syntax to show structure
- DON'T write code: Show interfaces/APIs conceptually, not literally
- LINK extensively: Reference existing components with [name](path)
- JUSTIFY decisions: Explain the "why" for each major choice
- Be CONCISE: Architecture is 200-500 words total, not a novel

Example component description:
```
**UserAuthService**: Handles authentication and session management.
Technology: JWT tokens with Redis session store (matches existing 
SessionManager pattern in [auth/session.ts](path)).
Rationale: Stateless auth enables horizontal scaling.
```

NO: Step-by-step implementation instructions
NO: Detailed code examples
NO: Testing strategies (that's for later phases)
</output_guidelines>

<quality_checks>
Before presenting architecture, verify:

- [ ] No implementation steps or numbered action lists
- [ ] All components have clear, single responsibilities  
- [ ] Decisions are justified with rationale
- [ ] Technology choices fit existing stack
- [ ] Open questions are clearly flagged
- [ ] Document is 200-500 words (excluding diagrams)

If any check fails, revise before presenting.
</quality_checks>
```
