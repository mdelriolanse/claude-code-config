# Claude Code Configs

Custom configurations for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Structure

```
.claude/
├── SKILLS/      # Agent personas for different tasks
└── commands/    # Slash commands for workflows
```

## Skills

Drop these in your `.claude/SKILLS/` folder. Each defines a specialized mode:

- **architect** - Systems design with trade-off analysis and diagrams
- **debugger** - Structured debugging with hypothesis/verification loops
- **explainer** - First-principles explanations at varying depth levels
- **planner** - Phased planning with risk assessment
- **ponderer** - Step-by-step reasoning with visible thinking
- **surveyor** - Codebase investigation (read-only, no suggestions)

Trigger them by including the keyword in your prompt, e.g. `[ARCHITECT] design a caching layer for...`

## Commands

Slash commands for common workflows. Some require MCP servers (Playwright, Firecrawl).

- `/prime` - Orient the agent to your codebase structure and tech stack
- `/build [feature]` - Implement a feature following project patterns
- `/plan [requirement]` - Generate a detailed implementation plan
- `/load-docs [url]` - Scrape docs into local markdown (requires Firecrawl)
- `/network-audit [url]` - Analyze page weight and API health (requires Playwright)
- `/ui-regress [local] [prod]` - Visual diff between local and production (requires Playwright)
- `/parallel-audit [dir]` - Run security and performance audits in parallel
- `/update-context-bundles [scope]` - Refresh JSON context bundles after project changes
- `/document-issue [issue-name]` - Documents issue with attempted fixes and potential avenues to explore.

## Installation

Copy to your project root or `~/.claude/` for global use.
