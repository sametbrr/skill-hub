[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/agentskills.io-compatible-blue)](https://agentskills.io)

[Quick Start](#quick-start) • [Features](#features) • [Installation](#installation) • [Usage](#usage) • [How It Works](#how-it-works) • [Contributing](#contributing)

# skill-hub

Plugin marketplace for Claude Code and OpenAI Codex: wiki management, conversation checkpoints, project discovery, model-aware prompt engineering, GitHub account tooling and encrypted secret sync.

> 🇹🇷 Türkçe için [README.tr.md](README.tr.md)

---

## Quick Start

```bash
# Claude Code
claude plugin marketplace add sametbrr/skill-hub
claude plugin install llm-wiki-manager@skill-hub

# Codex
codex plugin marketplace add sametbrr/skill-hub
codex plugin add llm-wiki-manager@skill-hub
```

Then ask in natural language, e.g. *"set up an LLM wiki here"*. No further configuration is needed for most plugins.

---

## Features

| Plugin | What it does | Claude Code | Codex |
|---|---|:---:|:---:|
| [llm-wiki-manager](https://github.com/sametbrr/llm-wiki-manager) | Personal LLM-managed wiki: ingest sources, cross-reference pages, query with citations, lint | ✓ | ✓ |
| [look-again](https://github.com/sametbrr/look-again) | Save conversation checkpoints as markdown and resume with full context; one folder shared by both agents | ✓ | ✓ |
| [prompt-architect](https://github.com/sametbrr/prompt-architect) | Turn a rough request into an expert prompt tuned to the detected Claude or OpenAI/Codex model, with a 12-gate review | ✓ | ✓ |
| [github-manager](https://github.com/sametbrr/github-manager) | Audit and strengthen any GitHub account: profile, profile README, descriptions, topics, READMEs, release workflows (bundles readme-standard) | ✓ | ✓ |
| [crypt-sync](https://github.com/sametbrr/crypt-sync) | Keep `.env` and secret files encrypted in git, synced across machines via age — **needs `npm install -g crypt-sync`** | ✓ | ✓ |
| [project-radar](https://github.com/sametbrr/project-radar) | Daily Turkish HTML radar report of trending GitHub projects with a persistent watchlist | ✓ | — |

Every plugin entry is pinned to a release tag, so installs and updates only pick up released versions.

---

## Requirements

- Claude Code or OpenAI Codex CLI (latest)
- Plugin-specific requirements are listed in each plugin's own README
- `crypt-sync` also needs its CLI on `PATH`: `npm install -g crypt-sync` (Node.js 22 or later, LTS). The plugin is the agent layer; the encryption engine is the npm package

---

## Installation

**Claude Code**

```bash
claude plugin marketplace add sametbrr/skill-hub
claude plugin install <plugin>@skill-hub          # e.g. prompt-architect@skill-hub
claude plugin marketplace update skill-hub        # pick up new releases
```

**Codex**

```bash
codex plugin marketplace add sametbrr/skill-hub
codex plugin add <plugin>@skill-hub
codex plugin marketplace upgrade skill-hub        # pick up new releases
```

**Any other Agent Skills client** (Copilot, Cursor, Gemini CLI, …)

```bash
gh skill install sametbrr/<plugin> --agent <agent-name>
```

---

## Usage

Skills trigger from natural language. You can also pick one explicitly (`/plugin:skill` in Claude Code, the skill picker or a skill mention in Codex). Each plugin's README covers full usage.

| Plugin | Example triggers |
|---|---|
| llm-wiki-manager | "second brain", "add this to my wiki", "health check the wiki" |
| look-again | "look again", "look again list", "continue where we left off" |
| prompt-architect | "prompt yaz", "refine my prompt", "write this for Opus 5.5 / GPT-6.1" |
| github-manager | `gh-onboard`, `gh-audit`, `gh-normalize`, `profile-bio`, `profile-readme`, `readme-standard`, `release-workflow` |
| crypt-sync | ".env şifrele", "secret sync", "encrypt my env files" |
| project-radar | "radar çalıştır", "github trending raporu" |

---

## How It Works

Each plugin is its own GitHub repository with its own semver tags, and works in both hosts:

```
plugin-name/
├── .claude-plugin/plugin.json   → Claude Code manifest
├── .codex-plugin/plugin.json    → Codex manifest (same name and version)
├── skills/<skill>/SKILL.md      → one folder per skill, with references/, scripts/, assets/
├── agents/, hooks/              → optional Claude Code subagents and hooks
├── AGENTS.md                    → guide for any agent working on the repo (CLAUDE.md imports it)
└── README.md / README.tr.md
```

This repository holds only `.claude-plugin/marketplace.json`, which both Claude Code and Codex read. Each entry points to a plugin repository at a release tag.

---

## Project Structure

```
skill-hub/
├── .claude-plugin/
│   └── marketplace.json   → catalog read by Claude Code and Codex
├── README.md / README.tr.md
└── LICENSE
```

For local development the plugin repositories can be cloned next to the catalog (`skill-hub/<plugin>/`); they are git-ignored here.

---

## Contributing

- Questions and ideas: [Discussions](https://github.com/sametbrr/skill-hub/discussions)
- Bugs: [issue tracker](https://github.com/sametbrr/skill-hub/issues)
- Pull requests: read the [contribution guide](https://github.com/sametbrr/.github/blob/main/CONTRIBUTING.md) first
- Security reports: follow the [security policy](https://github.com/sametbrr/skill-hub/security/policy), not a public issue

---

## License

MIT — see [LICENSE](LICENSE).
