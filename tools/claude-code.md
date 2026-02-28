# Claude Code

> AI-powered CLI that operates as a general-purpose work tool — engineering, hiring, research, strategy, and operations from the terminal.

## What It Is

Claude Code is Anthropic's agentic coding tool that operates directly in the terminal. It understands entire codebases, edits files, runs commands, and handles multi-step engineering tasks autonomously. It works with any language, framework, or toolchain — no IDE plugins or configuration required.

## Why We Use It

Most AI coding assistants are bolted onto editors and limited to single-file suggestions. Claude Code operates at the project level — it reads across files, understands architecture, runs tests, and iterates on its own output. But we've found it's far more than a coding tool. Because it has access to the terminal, MCP servers, and custom slash commands, it functions as a general-purpose operator — writing proposals, summarizing interviews, managing hiring workflows, and coordinating across tools. For a small team where everyone wears multiple hats, having one interface that handles engineering, ops, and strategy work means less context-switching and faster execution across the board.

## How We Use It

### Software Engineering

Feature development, debugging, refactoring, test writing, and PR workflows. A `CLAUDE.md` in each repo gives Claude persistent context about architecture and conventions across sessions.

### Operations and Communications

Drafting candidate assessments, offer letters, partnership proposals, strategy documents, and investor materials. Claude Code handles the writing while we stay focused on decisions.

### Research Synthesis

Querying multiple sources via MCP servers — screen recordings, Slack threads, scientific literature — and synthesizing scattered information into structured output.

### Custom Workflows

Slash commands in `~/.claude/commands/` turn repeatable multi-step processes into single invocations, often dispatching parallel agents to gather and synthesize information.

### Tool Unification via MCP

Screenpipe, Slack, PubMed, and other services are connected as MCP servers, making Claude Code a single interface for search, communication, and research.

## Getting Started

1. Install Claude Code:
   ```bash
   curl -fsSL https://claude.ai/install.sh | sh
   ```
2. Run it:
   ```bash
   claude
   ```
3. Add a `CLAUDE.md` to your project root with architecture context and conventions.
4. Configure MCP servers in `~/.claude.json` for tool integrations (Screenpipe, Slack, etc.).
5. Add custom slash commands in `~/.claude/commands/` for repeatable workflows.

## Links

- [Official site](https://claude.ai/code)
- [Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [GitHub](https://github.com/anthropics/claude-code)
