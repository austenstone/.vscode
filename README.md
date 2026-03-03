# 🎯 Austen's VS Code Configuration

> My personal VS Code Insiders configuration — custom Copilot agents, instructions, MCP servers, and settings that power my day-to-day development ✨

[![Clone in VS Code](https://img.shields.io/badge/Clone_Repo-VS_Code-0098FF?style=for-the-badge&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3A%2F%2Fvscode.git%2Fclone%3Furl%3Dhttps%3A%2F%2Fgithub.com%2Faustenstone%2F.vscode.git)
[![Clone in VS Code Insiders](https://img.shields.io/badge/Clone_Repo-VS_Code_Insiders-24bfa5?style=for-the-badge&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3A%2F%2Fvscode.git%2Fclone%3Furl%3Dhttps%3A%2F%2Fgithub.com%2Faustenstone%2F.vscode.git)

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
| [Beast Mode 2.0](prompts/Beast%20Mode%202.0.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FBeast%2520Mode%25202.0.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FBeast%2520Mode%25202.0.agent.md) | GPT-5 autonomous agent for complex problems |
| [CCA Orchestrator](prompts/Copilot%20CCA%20Orchestrator.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FCopilot%2520CCA%2520Orchestrator.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FCopilot%2520CCA%2520Orchestrator.agent.md) | Breaks large tasks into separate PRs for Copilot Coding Agents |
| [Create Copilot Agent](prompts/Copilot%20Customization.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FCopilot%2520Customization.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FCopilot%2520Customization.agent.md) | AI Agent for creating GitHub Copilot agents |
| [GitHub Models](prompts/GitHub%20Models.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FGitHub%2520Models.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FGitHub%2520Models.agent.md) | Creates prompt files for GitHub Models with evaluators and test cases |
| [Plan+](prompts/Plan.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FPlan.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FPlan.agent.md) | Researches and outlines multi-step plans |
| [Refine Prompt](prompts/Refine%20Prompt.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FRefine%2520Prompt.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FRefine%2520Prompt.agent.md) | Refine prompts for clarity, completeness, and unambiguity |
| [Research](prompts/Research.agent.md)<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FResearch.agent.md) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Achat-agent%2Finstall%3Furl%3Dhttps%3A%2F%2Fraw.githubusercontent.com%2Faustenstone%2F.vscode%2Fmain%2Fprompts%2FResearch.agent.md) | Research mode for gathering information and analyzing topics |

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

The [mcp.json](mcp.json) file configures 20+ Model Context Protocol servers. Click **Install** to add any server to your VS Code.

> **Note:** GitHub's built-in MCP servers (GitHub MCP, Context, Security, Actions, Copilot, Projects, Discussions) are automatically available — no install needed.

| Server | Description |
|--------|-------------|
| **Sequential Thinking**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22sequentialthinking%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40modelcontextprotocol%2Fserver-sequential-thinking%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22sequentialthinking%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40modelcontextprotocol%2Fserver-sequential-thinking%22%5D%2C%22type%22%3A%22stdio%22%7D) | Step-by-step reasoning for complex problems |
| **Playwright**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22playwright%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22%40playwright%2Fmcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22playwright%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22%40playwright%2Fmcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) | Browser automation and testing |
| **Context7**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22context7%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22%40upstash%2Fcontext7-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22context7%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22%40upstash%2Fcontext7-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) | Up-to-date library documentation lookup |
| **Brave Search**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22brave-search%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40brave%2Fbrave-search-mcp-server%22%2C%22--transport%22%2C%22stdio%22%5D%2C%22env%22%3A%7B%22BRAVE_API_KEY%22%3A%22%24%7Binput%3Abrave-api-key%7D%22%7D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22brave-search%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40brave%2Fbrave-search-mcp-server%22%2C%22--transport%22%2C%22stdio%22%5D%2C%22env%22%3A%7B%22BRAVE_API_KEY%22%3A%22%24%7Binput%3Abrave-api-key%7D%22%7D%2C%22type%22%3A%22stdio%22%7D) | Web search via Brave API |
| **Firecrawl**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22firecrawl-mcp%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22firecrawl-mcp%22%5D%2C%22env%22%3A%7B%22FIRECRAWL_API_KEY%22%3A%22%24%7Binput%3AFIRECRAWL_API_KEY%7D%22%7D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22firecrawl-mcp%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22firecrawl-mcp%22%5D%2C%22env%22%3A%7B%22FIRECRAWL_API_KEY%22%3A%22%24%7Binput%3AFIRECRAWL_API_KEY%7D%22%7D%2C%22type%22%3A%22stdio%22%7D) | Web scraping and crawling |
| **MarkItDown**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22markitdown%22%2C%22command%22%3A%22uvx%22%2C%22args%22%3A%5B%22markitdown-mcp%3D%3D0.0.1a4%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22markitdown%22%2C%22command%22%3A%22uvx%22%2C%22args%22%3A%5B%22markitdown-mcp%3D%3D0.0.1a4%22%5D%2C%22type%22%3A%22stdio%22%7D) | Document conversion to Markdown |
| **Angular CLI**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22angular-cli%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40angular%2Fcli%22%2C%22mcp%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22angular-cli%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40angular%2Fcli%22%2C%22mcp%22%5D%2C%22type%22%3A%22stdio%22%7D) | Angular project scaffolding |
| **Chrome DevTools**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22chrome-devtools%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22chrome-devtools-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22chrome-devtools%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22chrome-devtools-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) | Chrome browser debugging |
| **Mobile MCP**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22mobile-mcp%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22%40mobilenext%2Fmobile-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22mobile-mcp%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22%40mobilenext%2Fmobile-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) | Mobile device automation |
| **WorkIQ**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22workiq%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40microsoft%2Fworkiq%22%2C%22mcp%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22workiq%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40microsoft%2Fworkiq%22%2C%22mcp%22%5D%2C%22type%22%3A%22stdio%22%7D) | Microsoft Work IQ integration |
| **NotebookLM**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22notebooklm%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22notebooklm-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22notebooklm%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22notebooklm-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) | Google NotebookLM integration |
| **MyInstants**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22myinstants%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22myinstants-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22myinstants%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22myinstants-mcp%40latest%22%5D%2C%22type%22%3A%22stdio%22%7D) | Sound effects 🔊 |
| **Time**<br/>[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22time%22%2C%22command%22%3A%22uvx%22%2C%22args%22%3A%5B%22mcp-server-time%22%2C%22--local-timezone%22%2C%22America%2FNew_York%22%5D%2C%22type%22%3A%22stdio%22%7D) [![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://austenstone.github.io/.vscode/install/?url=vscode-insiders%3Amcp%2Finstall%3F%7B%22name%22%3A%22time%22%2C%22command%22%3A%22uvx%22%2C%22args%22%3A%5B%22mcp-server-time%22%2C%22--local-timezone%22%2C%22America%2FNew_York%22%5D%2C%22type%22%3A%22stdio%22%7D) | Timezone-aware time utilities |

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

### Option 2: Install individual agents or MCP servers
Click any **Install in VS Code** badge above to add a single agent or MCP server to your setup.

### Option 3: Browse and adapt
1. Explore the [`prompts/`](prompts/) folder for agents, instructions, and prompts
2. Check [`mcp.json`](mcp.json) for MCP server configurations
3. Review [`settings.json`](settings.json) for VS Code customizations
4. Adapt patterns to your own workflow

> 💡 **Tip:** Learn more about customizing Copilot in the [official docs](https://code.visualstudio.com/docs/copilot/customization/overview) or browse [awesome-copilot](https://github.com/github/awesome-copilot) for community contributions.
