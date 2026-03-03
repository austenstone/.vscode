# 🎯 Austen's VS Code Configuration

> My personal VS Code Insiders configuration — custom Copilot agents, instructions, MCP servers, and settings that power my day-to-day development ✨

[![Clone in VS Code](https://img.shields.io/badge/Clone_Repo-VS_Code-0098FF?style=for-the-badge&logo=visualstudiocode&logoColor=white)](vscode://vscode.git/clone?url=https://github.com/austenstone/.vscode.git)
[![Clone in VS Code Insiders](https://img.shields.io/badge/Clone_Repo-VS_Code_Insiders-24bfa5?style=for-the-badge&logo=visualstudiocode&logoColor=white)](vscode-insiders://vscode.git/clone?url=https://github.com/austenstone/.vscode.git)

## 📖 What is Copilot Customization?

VS Code lets you customize GitHub Copilot through simple files in your workspace. Here's the taxonomy:

| Type | File | Purpose |
|------|------|---------|
| 🤖 **Custom Agents** | `.agent.md` | AI personas with specific tools and behaviors |
| 📋 **Instructions** | `.instructions.md` | Always-on coding standards and rules |
| 💬 **Prompt Files** | `.prompt.md` | Reusable task templates invoked as slash commands |
| 🔌 **MCP Servers** | `mcp.json` | External tool/API integrations |

> 📚 [VS Code Copilot Customization Docs](https://code.visualstudio.com/docs/copilot/customization/overview) · [awesome-copilot](https://github.com/github/awesome-copilot) for community-contributed agents, instructions, and more

---

## 🤖 Custom Agents

Click **Install** to add any agent directly to your VS Code with one click.

| Agent | Description |
|-------|-------------|
| [Beast Mode 2.0](prompts/Beast%20Mode%202.0.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Beast%20Mode%202.0.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Beast%20Mode%202.0.agent.md) | GPT-5 autonomous agent for complex problems |
| [CCA Orchestrator](prompts/Copilot%20CCA%20Orchestrator.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Copilot%20CCA%20Orchestrator.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Copilot%20CCA%20Orchestrator.agent.md) | Breaks large tasks into separate PRs for Copilot Coding Agents |
| [Create Copilot Agent](prompts/Copilot%20Customization.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Copilot%20Customization.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Copilot%20Customization.agent.md) | AI Agent for creating GitHub Copilot agents |
| [GitHub Models](prompts/GitHub%20Models.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/GitHub%20Models.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/GitHub%20Models.agent.md) | Creates prompt files for GitHub Models with evaluators and test cases |
| [Plan+](prompts/Plan.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Plan.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Plan.agent.md) | Researches and outlines multi-step plans |
| [Refine Prompt](prompts/Refine%20Prompt.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Refine%20Prompt.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Refine%20Prompt.agent.md) | Refine prompts for clarity, completeness, and unambiguity |
| [Research](prompts/Research.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Research.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](vscode-insiders:chat-agent/install?url=https://raw.githubusercontent.com/austenstone/.vscode/main/prompts/Research.agent.md) | Research mode for gathering information and analyzing topics |

---

## 📋 Instructions

Always-on rules that automatically apply to matching files.

| File | Applies To | Purpose |
|------|-----------|---------|
| [personal.instructions.md](prompts/personal.instructions.md) | `**` | Personal preferences, identity, communication style |
| [se.instructions.md](prompts/se.instructions.md) | `**` | GitHub Solutions Engineer work context and team roster |
| [typescript.instructions.md](prompts/typescript.instructions.md) | `**/*.ts, **/*.tsx, **/*.js, **/*.jsx` | Modern TypeScript/JavaScript coding standards |
| [github-actions.instructions.md](prompts/github-actions.instructions.md) | `.github/**/*.yml, .github/**/*.yaml` | GitHub Actions CI/CD security and best practices |
| [GitHub Markdown.instructions.md](prompts/GitHub%20Markdown.instructions.md) | `**/*.md` | Comprehensive GitHub Markdown style guide |
| [agents.instructions.md](prompts/agents.instructions.md) | `.github/agents/*.md` | Custom agent `.agent.md` schema reference |
| [copilot-instructions.instructions.md](prompts/copilot-instructions.instructions.md) | `**/copilot-instructions.md, **/*.instructions.md` | Guidelines for writing effective instruction files |

---

## 💬 Prompt Files

Reusable task templates — run them as slash commands in chat.

| Prompt | Description |
|--------|-------------|
| [create-instructions.prompt.md](prompts/create-instructions.prompt.md) | Analyze a codebase and generate tailored instruction files |
| [awesome-copilot-suggestions.prompt.md](prompts/awesome-copilot-suggestions.prompt.md) | Suggest and install collections from [awesome-copilot](https://github.com/github/awesome-copilot) |
| [model-compare.prompt.md](prompts/model-compare.prompt.md) | Generate a comprehensive Copilot model comparison guide |
| [resume-review.prompt.md](prompts/resume-review.prompt.md) | Expert resume reviewer with structured JSON output |

---

## 🔌 MCP Servers

The [mcp.json](mcp.json) file configures 20+ Model Context Protocol servers. Featured servers:

| Server | Type | Description |
|--------|------|-------------|
| **GitHub MCP** | HTTP | Full GitHub API — repos, issues, PRs, actions, security, discussions, projects |
| **Playwright** | stdio | Browser automation and testing |
| **Brave Search** | stdio | Web search via Brave API |
| **Context7** | stdio | Up-to-date library documentation lookup |
| **Sequential Thinking** | stdio | Step-by-step reasoning for complex problems |
| **Firecrawl** | stdio | Web scraping and crawling |
| **MarkItDown** | stdio | Document conversion to Markdown |
| **WorkIQ** | stdio | Microsoft Work IQ integration |
| **NotebookLM** | stdio | Google NotebookLM integration |
| **Angular CLI** | stdio | Angular project scaffolding |
| **Chrome DevTools** | stdio | Chrome browser debugging |
| **Mobile MCP** | stdio | Mobile device automation |
| **MyInstants** | stdio | Sound effects 🔊 (yes, really) |
| **Time** | stdio | Timezone-aware time utilities |

---

## 📂 Repository Structure

```
prompts/
├── *.agent.md          # 7 custom agents (Beast Mode, Plan+, Research, etc.)
├── *.instructions.md   # 7 always-on instruction files
└── *.prompt.md         # 4 reusable prompt templates
mcp.json                # 20+ MCP server configurations
settings.json           # VS Code Insiders settings
keybindings.json        # Custom keyboard shortcuts
```

---

## 🚀 Quick Start

### Option 1: Clone the repo
Click the badge at the top, or:
```bash
git clone https://github.com/austenstone/.vscode.git
```

### Option 2: Install individual agents
Click any **Install in VS Code** badge above to add a single agent to your setup.

### Option 3: Browse and adapt
1. Explore the [`prompts/`](prompts/) folder for agents, instructions, and prompts
2. Check [`mcp.json`](mcp.json) for MCP server configurations
3. Review [`settings.json`](settings.json) for VS Code customizations
4. Adapt patterns to your own workflow

> 💡 **Tip:** Learn more about customizing Copilot in the [official docs](https://code.visualstudio.com/docs/copilot/customization/overview) or browse [awesome-copilot](https://github.com/github/awesome-copilot) for community contributions.
