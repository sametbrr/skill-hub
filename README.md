[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

# skill-hub

Claude Code skill collection — wiki management, conversation checkpoints, NotebookLM automation, project discovery, prompt engineering and README tooling.

> 🇹🇷 Türkçe için [README.tr.md](README.tr.md)

---

## Quick Start

Install any plugin directly from its GitHub repository:

```bash
claude plugin install github:sametbrr/llm-wiki-manager
```

Then invoke it in Claude Code:

```
/llm-wiki-manager bootstrap
```

No further configuration is needed for most plugins.

---

## Features

| Plugin | What it does |
|---|---|
| [llm-wiki-manager](https://github.com/sametbrr/llm-wiki-manager) | Personal LLM-managed wiki: ingest sources, cross-reference pages, query with citations, lint |
| [look-again](https://github.com/sametbrr/look-again) | Save conversation checkpoints as markdown files and resume with full context |
| [notebooklm](https://github.com/sametbrr/notebooklm) | Full programmatic access to Google NotebookLM: notebooks, podcasts, quizzes and more |
| [project-radar](https://github.com/sametbrr/project-radar) | Daily Turkish HTML radar report of trending GitHub projects with a persistent watchlist |
| [prompt-architect](https://github.com/sametbrr/prompt-architect) | Turn any rough request into a structured, domain-aware expert prompt with an 8-gate review |
| [readme-standard](https://github.com/sametbrr/readme-standard) | Enforce consistent README.md + README.tr.md structure: create, audit, fix and TR-sync modes |

---

## Requirements

- Claude Code CLI (latest)
- Plugin-specific requirements are listed in each plugin's own README

---

## Installation

**Option 1 — Marketplace (recommended):** Register the hub once, then install any plugin by name.

```bash
claude plugin marketplace add sametbrr/skill-hub
claude plugin install llm-wiki-manager@sametbrr/skill-hub
```

**Option 2 — Individual install:** Install any plugin directly from its own repository.

```bash
claude plugin install github:sametbrr/llm-wiki-manager
claude plugin install github:sametbrr/look-again
claude plugin install github:sametbrr/notebooklm
claude plugin install github:sametbrr/project-radar
claude plugin install github:sametbrr/prompt-architect
claude plugin install github:sametbrr/readme-standard
```

---

## Usage

Each plugin registers a skill that Claude Code picks up automatically after installation. Refer to the individual plugin README for full usage and configuration.

| Plugin | Trigger |
|---|---|
| llm-wiki-manager | `/llm-wiki-manager` or mention "second brain", "wiki", "Memex" |
| look-again | `/look-again` |
| notebooklm | `/notebooklm` or "create a podcast about X" |
| project-radar | `/project-radar` or "radar çalıştır" |
| prompt-architect | `/prompt-architect` or "prompt yaz", "refine my prompt" |
| readme-standard | `/readme-standard` |

---

## How It Works

Each plugin in this hub follows the same structure:

```
plugin-name/
├── SKILL.md              → skill definition loaded by Claude Code
├── .claude-plugin/
│   └── plugin.json       → marketplace metadata
├── assets/               → templates and static resources
├── references/           → reference docs read at runtime
└── scripts/              → helper scripts (Python, where needed)
```

`SKILL.md` is the entry point — it defines the skill name, description, and instructions Claude follows when the skill is invoked. `plugin.json` registers the plugin in the marketplace so it can be discovered and installed.

---

## Project Structure

```
skill-hub/
├── llm-wiki-manager/     → personal wiki management
├── look-again/           → conversation checkpoints
├── notebooklm/           → Google NotebookLM automation
├── project-radar/        → GitHub trending radar
├── prompt-architect/     → expert prompt engineering
├── readme-standard/      → README enforcement
└── .claude-plugin/
    └── marketplace.json  → hub-level marketplace index
```

Each subdirectory is also an independent git repository and can be used standalone.

---

## License

MIT — see [LICENSE](LICENSE).
