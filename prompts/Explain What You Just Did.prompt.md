---
agent: agent
---
Based on the task you just completed, write a reusable prompt that would instruct a fresh instance of yourself to replicate this success without trial and error.

Output the prompt inside a code block. You must strictly follow this XML structure:

<instructions>
  <task>
    [Summarize the objective of the task]
  </task>
  
  <steps>
    [List the specific, optimal logic steps taken. Remove any failed attempts or back-tracking. Number them 1, 2, 3...]
  </steps>

  <formatting>
    [Define the required output format (e.g., JSON, markdown list, specific constraints)]
  </formatting>
</instructions>