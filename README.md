<img src="assets/banner.png" width="100%" alt="Ellmos banner">

<p align="center">
  <img src="ellmos-logo.jpg" alt="ellmos logo" width="400">
</p>

# ellmos -- Extra Large Language Model Operating Systems

*From a spring to a stream -- LLM operating systems that flow.*

**English** | [Deutsch](README_de.md)

![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![SQLite](https://img.shields.io/badge/Database-SQLite-003B57?logo=sqlite)
![LLM-Ready](https://img.shields.io/badge/LLM-Ready-blueviolet?logo=openai)
![Local-First](https://img.shields.io/badge/Architecture-Local--First-informational)
![MCP](https://img.shields.io/badge/MCP-Supported-8A2BE2?logo=anthropic)

**ellmos** (XLLM-OS) is a local-first family of text-based operating systems for Large Language Models: agent memory, task state, MCP tools, skills, connector bridges, model routing, and multi-agent orchestration in small SQLite-backed projects. It is designed for people who want an AI operating layer they can inspect, run locally, and extend without a hosted platform.

> [!NOTE]
> **Machine-Readable Index**: For AI agents, LLM tool callers, and automated indexing engines, a full context directory and system breakdown is available in [`llms.txt`](llms.txt).

> **Quick links:** [Organization](https://github.com/ellmos-ai) | [BACH](https://github.com/ellmos-ai/bach) | [Rinnsal](https://github.com/ellmos-ai/rinnsal) | [gardener](https://github.com/ellmos-ai/gardener) | [llms.txt](llms.txt)

## Start Here

| If you are looking for... | Start with | Why |
|---|---|---|
| A full personal LLM operating system with GUI, skills, scheduler, bridges, and multi-agent workflows | [BACH](https://github.com/ellmos-ai/bach) | Largest ellmos system and the main integration point |
| A lightweight Python infrastructure layer for memory, tasks, connectors, and chains | [Rinnsal](https://github.com/ellmos-ai/rinnsal) | Small, local-first, dependency-light foundation |
| A minimal LLM-native SQLite experiment | [gardener](https://github.com/ellmos-ai/gardener) | One-table operating substrate for simple agents |
| Shared memory, model routing, chains, or parallel agent patterns | [USMC](https://github.com/ellmos-ai/usmc), [clutch](https://github.com/ellmos-ai/clutch), [MarbleRun](https://github.com/ellmos-ai/MarbleRun), [swarm-ai](https://github.com/ellmos-ai/swarm-ai) | Standalone modules that can be combined with any OS tier |
| MCP servers for Claude Code, Cursor, or other AI IDEs | [CodeCommander](https://github.com/ellmos-ai/ellmos-codecommander-mcp), [FileCommander](https://github.com/ellmos-ai/ellmos-filecommander-mcp), [n8n Manager](https://github.com/ellmos-ai/n8n-manager-mcp), [ControlCenter](https://github.com/ellmos-ai/ellmos-controlcenter-mcp), [Homebase](https://github.com/ellmos-ai/ellmos-homebase-mcp), [ServerCommander](https://github.com/ellmos-ai/ellmos-servercommander-mcp) | Tool servers for code, files, workflows, local state, and local control planes |

---

## Which OS Should I Use?

| Question | BACH | Rinnsal | gardener |
|----------|------|---------|----------|
| I want a full-featured agent OS with GUI, skills, and multi-agent orchestration | **Yes** | | |
| I want lightweight LLM infrastructure with zero dependencies | | **Yes** | |
| I want the simplest possible LLM-native OS (1 table, 4 functions) | | | **Yes** |
| I need Telegram/Email/WhatsApp connectors | **Yes** | **Yes** | Planned |
| I want to self-extend with new skills at runtime | **Yes** | | |
| I want minimal footprint (~2k lines) | | **Yes** | **Yes** |

---

## The ellmos Family

### BACH -- The stream that unites everything

The full LLM operating system. 113+ handlers, 550+ tools, 1870+ skills, 71 workflow templates, 11 boss agents with 22 experts, PySide6 desktop GUI, scheduler, bridge system, and self-extension via `bach skills create`.

```bash
git clone https://github.com/ellmos-ai/bach.git
cd bach && pip install -r requirements.txt
python system/setup.py
python bach.py --startup
```

**[Full BACH Documentation](https://github.com/ellmos-ai/bach)**

### Rinnsal -- The trickle

Lightweight LLM infrastructure: memory, tasks, connectors, chains. Zero external dependencies. Everything BACH does conceptually, but in ~2,000 lines for developers who want to build their own agent on top.

```bash
git clone https://github.com/ellmos-ai/rinnsal.git
cd rinnsal && pip install -r requirements.txt
```

**[Full Rinnsal Documentation](https://github.com/ellmos-ai/rinnsal)**

### gardener -- The zen garden

LLM-native OS: one `everything` table, 4 functions, FTS5 full-text search -- split across two databases (`gardener.db` for system knowledge, `user.db` for your data) that one query searches together. Everything is searchable. The LLM *is* the agent -- gardener just provides the soil.

```bash
git clone https://github.com/ellmos-ai/gardener.git
cd gardener && pip install -r requirements.txt
```

**[Full gardener Documentation](https://github.com/ellmos-ai/gardener)**

---

## Architecture: 3 OS Layers + Pluggable Modules

```
+-------------------------------------------------+
|              Choose Your OS Layer               |
|                                                 |
|   BACH (full)   Rinnsal (light)  gardener (min) |
|   +---------+   +------------+   +----------+  |
|   | 1870+   |   | Zero deps  |   | 1 table  |  |
|   | skills  |   | Connectors |   | 4 funcs  |  |
|   | 11 boss |   | Chains     |   | FTS5     |  |
|   | agents  |   | Events     |   | = search |  |
|   +----+----+   +-----+------+   +-----+----+  |
|        +---------------+----------------+       |
|                        |                        |
|        +---------------+---------------+        |
|        |    Pluggable Modules          |        |
|        |                               |        |
|        |  USMC      -- shared memory   |        |
|        |  clutch    -- model routing   |        |
|        |  MarbleRun -- agent chains    |        |
|        |  swarm-ai  -- parallel LLMs   |        |
|        +-------------------------------+        |
+-------------------------------------------------+
```

### Detailed Comparison

| | **BACH** | **Rinnsal** | **gardener** |
|---|---|---|---|
| **Philosophy** | Maximalist: everything integrated | Lightweight: zero dependencies | Minimalist: 1 table, 4 functions |
| **Database** | SQLite (210+ tables) | SQLite (structured) | SQLite (1 table `everything` + FTS5, across 2 files) |
| **Memory** | 6 memory types with decay, conflict detection, consolidation | Facts/Notes/Lessons/Sessions | Unified (memo/lesson/recall + decay) |
| **Tasks** | Full GTD (priority, deadline, tags) | Priority + Status + Agent assignment | type='task' in everything |
| **Tools** | 550+ specialized tools | CLI commands | 6 bridge+skin tools (extensible) |
| **Skills/Agents** | 1870+ skills, 11 boss agents, 22 experts | None | None (the LLM is the agent) |
| **Connectors** | Telegram, Email, WhatsApp | Telegram, Discord, Home Assistant | Planned (v0.2+) |
| **GUI** | PySide6 Desktop + Web | CLI only | CLI only |
| **Self-Extension** | `bach skills create` | No | No |
| **Codebase** | ~50,000+ lines | ~2,000 lines | ~1,600 lines |
| **Best for** | Power users, all-in-one | Developers wanting light infra | Minimalists, LLM-native experiments |

---

## Pluggable Modules

These modules integrate into any ellmos OS -- or work standalone:

| Module | Purpose | Key Feature | Repo |
|---|---|---|---|
| **USMC** | Cross-agent shared memory | Confidence-based conflict resolution, change tracking | [ellmos-ai/usmc](https://github.com/ellmos-ai/usmc) |
| **clutch** | Provider-neutral model routing | Auto-learning which model fits which task, budget zones | [ellmos-ai/clutch](https://github.com/ellmos-ai/clutch) |
| **MarbleRun** | Chain orchestration | Autonomous multi-round agent loops with context handoff | [ellmos-ai/MarbleRun](https://github.com/ellmos-ai/MarbleRun) |
| **swarm-ai** | Parallel LLM coordination | 5 patterns: Epstein, Hierarchy, Stigmergy, Consensus, Specialist | [ellmos-ai/swarm-ai](https://github.com/ellmos-ai/swarm-ai) |

> **gardener has two roles, and both are current.** Run standalone, it is the minimal OS tier
> described above: one table, four functions, FTS5 search. Composed into the **.MEMORY pillar**, it
> is the organic cross-source index alongside [usmc](https://github.com/ellmos-ai/usmc) (the curated
> façade) and [taskplan](https://github.com/ellmos-ai/taskplan) (task state). Which role applies
> depends on how you deploy it — see the [organization profile](https://github.com/ellmos-ai) for
> the pillar view.

---

## MCP Servers

ellmos provides [Model Context Protocol](https://modelcontextprotocol.io/) servers for integration with Claude Code, Cursor, and other AI-powered IDEs:

| Server | Tools | Description | Install |
|--------|-------|-------------|---------|
| **[CodeCommander](https://github.com/ellmos-ai/ellmos-codecommander-mcp)** | 22 | Code analysis, refactoring, import management, JSON/encoding repair | `npm i -g ellmos-codecommander-mcp` |
| **[FileCommander](https://github.com/ellmos-ai/ellmos-filecommander-mcp)** | 46 | File management, batch operations, process control, async search, cloud-lock checks | `npm i -g ellmos-filecommander-mcp` |
| **[Clatcher](https://github.com/ellmos-ai/ellmos-clatcher-mcp)** | 12 | File repair, format conversion, duplicate detection, batch operations | `npm i -g ellmos-clatcher-mcp` |
| **[n8n Manager](https://github.com/ellmos-ai/n8n-manager-mcp)** | 18 | Create, update, back up, and manage n8n workflows | `npm i -g n8n-manager-mcp` |
| **[ControlCenter](https://github.com/ellmos-ai/ellmos-controlcenter-mcp)** | 20 | Alpha control plane for local MCP servers, Claude profiles, policy audits | `npm i -g ellmos-controlcenter-mcp` |
| **[Homebase](https://github.com/ellmos-ai/ellmos-homebase-mcp)** | 45 | Alpha MCP server for local LLM memory, knowledge, state, routing, testing, and orchestration | See repo README |
| **[ServerCommander](https://github.com/ellmos-ai/ellmos-servercommander-mcp)** | 8 | Alpha MCP server for deploy dry-runs, mail status, log analysis, and server health checks | See repo README |
| **[Blender-Use](https://github.com/ellmos-ai/ellmos-blender-use-mcp)** | 3 | Headless Blender asset QA: background render, FBX re-import verification, script execution | `npm i -g ellmos-blender-use-mcp` |
| **[open-compute](https://github.com/ellmos-ai/open-compute-mcp)** | 10 | Computer-use over MCP: screen capture, semantic UI targeting via Windows UIA, canonical actions | `npm i -g open-compute-mcp` |

---

## More Projects

| Project | Description | Repo |
|---|---|---|
| **skills** | Pluggable skill library (dev, research, education, infrastructure) | [ellmos-ai/skills](https://github.com/ellmos-ai/skills) |
| **n8n Workflow Manager** | Standalone GUI for n8n workflow creation | [ellmos-ai/n8n-workflow-manager](https://github.com/ellmos-ai/n8n-workflow-manager) |
| **ellmos-stack** | Self-hosted AI stack (Docker, Ollama, n8n, memory, knowledge base) | [ellmos-ai/ellmos-stack](https://github.com/ellmos-ai/ellmos-stack) |
| **ellmos-tests** | Cross-OS test suite and benchmark reports | [ellmos-ai/ellmos-tests](https://github.com/ellmos-ai/ellmos-tests) |
| **stacks** | Catalog and shared manifest schema for every stack in the family | [ellmos-ai/stacks](https://github.com/ellmos-ai/stacks) |
| **agent-ops-stack** | Manifest-driven composition of the local agent-ops ecosystem | [ellmos-ai/agent-ops-stack](https://github.com/ellmos-ai/agent-ops-stack) |
| **connectors** | Portable messaging connectors: Telegram, Discord, Signal, WhatsApp, Home Assistant, Webhook | [ellmos-ai/connectors](https://github.com/ellmos-ai/connectors) |
| **open-compute** | Model-agnostic computer-use core for Claude, OpenAI CUA and mock backends | [ellmos-ai/open-compute](https://github.com/ellmos-ai/open-compute) |
| **web-scraper** | Standalone web scraper with SSRF guard, extracted from BACH | [ellmos-ai/web-scraper](https://github.com/ellmos-ai/web-scraper) |
| **taskplan** | Deterministic task selection so the backlog cannot hide | [ellmos-ai/taskplan](https://github.com/ellmos-ai/taskplan) |
| **anonymizer** | Local-first document pseudonymization with fail-closed NER | [ellmos-ai/anonymizer](https://github.com/ellmos-ai/anonymizer) |
| **report-forge** | Domain-neutral core for anonymizable report pipelines | [ellmos-ai/report-forge](https://github.com/ellmos-ai/report-forge) |
| **project-docs-template** | Agent-ready project documentation template (START/STATE/TODO/DONE) | [ellmos-ai/project-docs-template](https://github.com/ellmos-ai/project-docs-template) |
| **clirec** | Human-readable GUI demonstration recordings for CLI and agent workflows | [ellmos-ai/clirec](https://github.com/ellmos-ai/clirec) |
| **ai-media-editor** | Local AI editing for video, audio and podcasts with local transcription | [ellmos-ai/ai-media-editor](https://github.com/ellmos-ai/ai-media-editor) |
| **law-checker** | Source-grounded first-look legal assessments for German law | [ellmos-ai/law-checker](https://github.com/ellmos-ai/law-checker) |
| **steuer-assistent** | Offline-first worksheet for German employee income-related expenses | [ellmos-ai/steuer-assistent](https://github.com/ellmos-ai/steuer-assistent) |
| **worksheet-generator** | ICF-aware worksheets for pedagogical and therapeutic use | [ellmos-ai/worksheet-generator](https://github.com/ellmos-ai/worksheet-generator) |
| **build-your-users-mind** | Per-user theory of mind: a decision avatar built from interaction logs | [ellmos-ai/build-your-users-mind](https://github.com/ellmos-ai/build-your-users-mind) |

---

## Related Organizations

`ellmos-ai` is the AI-infrastructure part of a wider family of local-first projects. All four organizations below already link here; this is the way back.

| Organization | What lives there | Why it matters here |
|---|---|---|
| **[open-bricks](https://github.com/open-bricks)** | Umbrella profile for the whole family | Start here if you want the desktop, document, research and civic-tech projects alongside the AI infrastructure |
| **[dev-bricks](https://github.com/dev-bricks)** | Developer and multi-agent tooling: [lock-master](https://github.com/dev-bricks/lock-master), [ticket-master](https://github.com/dev-bricks/ticket-master), [sync-master](https://github.com/dev-bricks/sync-master) | [agent-ops-stack](https://github.com/ellmos-ai/agent-ops-stack) composes exactly these three as its coordination layer -- file locking, ticket routing and cross-machine sync -- and each of them also runs standalone |
| **[file-bricks](https://github.com/file-bricks)** | Local-first desktop tools for files, prompts and knowledge work: [knowledgedigest](https://github.com/file-bricks/knowledgedigest), [promptboard](https://github.com/file-bricks/promptboard) | [ellmos-stack](https://github.com/ellmos-ai/ellmos-stack) uses KnowledgeDigest as its document search layer |
| **[doc-bricks](https://github.com/doc-bricks)** | Document, mail, literature and note tools: [llm-note](https://github.com/doc-bricks/llm-note) | llm-note was extracted from BACH's notebook patterns and remains usable as a standalone agent-notes tool |

---

## Getting Started

1. **Pick your OS tier** using the comparison table above
2. **Clone and install** using the quick-start commands
3. **Optionally add modules** (USMC for shared memory, clutch for model routing, etc.)
4. **Add MCP servers** for IDE integration: `npm i -g ellmos-codecommander-mcp ellmos-filecommander-mcp`

All projects: **Python 3.10+** | **SQLite** | **MIT License** | **Zero or minimal dependencies**

---

## Search and Disambiguation

ellmos is the `ellmos-ai` local-first LLM operating-system family. It is not Eclipse LMOS, AllenAI OLMo, ELMo embeddings, Elmo Software, or a hosted agent platform. Useful search phrases include:

- `ellmos-ai ellmos local-first LLM operating system`
- `ellmos BACH Rinnsal gardener SQLite agent OS`
- `ellmos MCP CodeCommander FileCommander n8n Manager`
- `local-first LLM OS SQLite memory skills MCP`
- `Claude Code MCP local filesystem code analysis ellmos`
- `ellmos-ai ellmos canonical LLM OS namespace`

The canonical GitHub namespace is `ellmos-ai`. Older search-index snippets may still show `lukisch/ellmos` or legacy `bach-*` package names; use the `ellmos-ai/*` repositories and current `ellmos-*` MCP package names for new installs.

For automated indexing and AI assistants, see [`llms.txt`](llms.txt).

---

## License

All ellmos projects are released under the [MIT License](LICENSE).

## Links

- **Organization:** [github.com/ellmos-ai](https://github.com/ellmos-ai)
- **Author:** [Lukas Geiger](https://github.com/lukisch)

---

*ellmos -- Extra Large Language Model Operating Systems*
*The stream that unites everything.*
