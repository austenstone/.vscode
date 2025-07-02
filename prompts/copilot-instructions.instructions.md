---
applyTo: '**/copilot-instructions.md,**/*.instructions.md'
---
# GitHub Copilot Instruction Files Guidelines

## File Types
- **`.github/copilot-instructions.md`**: Workspace-wide instructions for all editors
- **`*.instructions.md`**: Context-specific instructions with `applyTo` targeting
- **VS Code settings**: For non-code tasks (commit messages, reviews, etc.)

## Structure Guidelines
- Use front matter with `applyTo` glob patterns for targeting
- Write in clear, simple Markdown format
- Keep each file focused on a single purpose
- Reference other instruction files with relative links

## Best Practices
- Start instructions with action verbs
- Use bullet points for lists of rules
- Include examples in code blocks when helpful
- Separate general and specific guidelines into different files
- Use `**` in `applyTo` for universal application

## Naming Conventions
- Use descriptive names: `typescript.instructions.md`, `api.instructions.md`
- Store workspace files in `.github/instructions/` 
- Keep user files organized by technology or purpose

## Content Guidelines
- Write short, single-statement instructions
- Avoid external references or links
- Focus on "how" rather than "what"
- Test instructions with actual code generation
