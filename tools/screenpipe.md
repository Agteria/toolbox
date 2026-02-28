# Screenpipe

> 24/7 screen and audio capture with AI-powered search — a personal memory layer for your workstation.

## What It Is

Screenpipe continuously records your screen and audio, stores everything locally, and makes it searchable through AI. It runs as a background service, capturing OCR'd text from your screen and transcribed audio from meetings and conversations. You can query it in natural language to find anything you've seen or heard.

## Why We Use It

Knowledge work produces a constant stream of context that disappears — Slack threads you half-read, terminal output you scrolled past, meeting details you didn't write down. Screenpipe captures all of it passively. Instead of relying on memory or manually logging everything, we have a searchable record of our actual work. This is especially valuable for a distributed team where context gets lost between async conversations, calls, and deep work sessions.

## How We Use It

### Meeting and Interview Recall

We capture audio from both microphone input and system output. After a meeting or interview, we query Screenpipe through Claude Code to pull full transcripts, extract key points, and draft follow-up documents — without having taken a single note during the conversation.

### Context Recovery via Claude Code

Screenpipe runs as an MCP server connected to Claude Code. This means we can ask Claude questions like "what was I working on before this conversation?" or "find what was discussed in the call this morning" directly from the terminal. Claude searches our screen and audio history, synthesizes the results, and responds in context.

### Passive Screen Capture

OCR runs continuously on the primary monitor at 0.5 fps, capturing everything visible — terminal output, Slack messages, browser content, documents. When something scrolls past or gets lost, we search for it later instead of trying to find it again manually.

### Local-Only Processing

All data stays on-device. No cloud sync, no third-party access. This is non-negotiable given the sensitivity of the work (research data, candidate interviews, internal communications).

## Getting Started

1. Clone the repo and build from source:
   ```bash
   git clone https://github.com/mediar-ai/screenpipe.git
   cd screenpipe
   cargo build --release
   ```
2. Run the server:
   ```bash
   ./target/release/screenpipe
   ```
3. Add the MCP server to your Claude Code config (`~/.claude.json`):
   ```json
   {
     "mcpServers": {
       "screenpipe": {
         "command": "npx",
         "args": ["-y", "screenpipe-mcp"]
       }
     }
   }
   ```
4. Verify it's working: ask Claude Code to "search screenpipe for what I was doing 5 minutes ago"

## Links

- [Official site](https://screenpi.pe)
- [Documentation](https://docs.screenpi.pe)
- [GitHub](https://github.com/mediar-ai/screenpipe)
