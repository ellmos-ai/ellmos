# ellmos - Extensive Large Language Model Operating Systems

*From a spring to a stream -- LLM operating systems that flow.*

![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)

## What is ellmos?

**ellmos** is a family of text-based operating systems that empower Large Language Models (LLMs) to work autonomously, learn, and self-organize. From a minimal shared memory layer to a full-featured OS with 100+ handlers, 900+ skills, and multi-agent orchestration -- pick the tier that fits your needs.

All ellmos projects follow a **water metaphor** -- growing from a spring to a stream:

## The ellmos Family

```
    USMC          Rinnsal              BACH
  the spring    the trickle    the stream that unites
     .             ~~~           ~~~~~~~~~~~
     :           ~~~~~~~       ~~~~~~~~~~~~~~~~~
     .         ~~~~~~~~~~~   ~~~~~~~~~~~~~~~~~~~~~~~
  (memory)    (+ llmauto)   (full system: 109+ handlers,
                              932+ skills, agents, GUI,
                              bridge, scheduler, wiki)
```

| Tier | Project | What it does | Repository |
|------|---------|-------------|------------|
| 1 | **USMC** | United Shared Memory Client -- minimal shared memory for multi-agent coordination | [lukisch/usmc](https://github.com/lukisch/usmc) |
| 2 | **Rinnsal** | The trickle -- USMC + llmauto for LLM chain orchestration, extremely compact | [lukisch/rinnsal](https://github.com/lukisch/rinnsal) |
| 3 | **BACH** | The stream that unites everything -- full LLM operating system | [lukisch/bach](https://github.com/lukisch/bach) |

## MCP Servers

ellmos provides MCP (Model Context Protocol) servers for integration with Claude Code, Cursor, and other IDEs:

| Server | Description | Install |
|--------|-------------|---------|
| **bach-codecommander-mcp** | Code analysis, refactoring, import management | `npm i -g bach-codecommander-mcp` |
| **bach-filecommander-mcp** | File management, batch operations, process control | `npm i -g bach-filecommander-mcp` |

## Quick Start

### Full System (BACH)

```bash
git clone https://github.com/lukisch/bach.git
cd bach
pip install -r requirements.txt
python system/setup.py
python bach.py --startup
```

### Minimal (Rinnsal)

```bash
git clone https://github.com/lukisch/rinnsal.git
cd rinnsal
pip install -r requirements.txt
```

### Memory Only (USMC)

```bash
git clone https://github.com/lukisch/usmc.git
cd usmc
pip install -r requirements.txt
```

## Key Features

### BACH (Full System)
- **109+ Handlers** -- Full CLI and API coverage
- **373+ Tools** -- File processing, analysis, automation
- **932+ Skills** -- Reusable workflows and templates
- **Agent Framework** -- Boss agents orchestrate expert agents
- **SharedMemory Bus** -- Multi-agent coordination with conflict detection
- **Bridge System** -- Telegram, Email, WhatsApp connectors
- **llmauto Chains** -- LLM prompt chains with `bach://` URL resolution
- **PySide6 GUI** -- Desktop dashboard with 32+ templates
- **Scheduler** -- Time-based and event-driven automation

### Rinnsal (Compact)
- USMC shared memory
- llmauto chain orchestration
- Minimal footprint, maximum LLM power

### USMC (Memory Layer)
- Cross-agent shared memory
- Conflict detection and resolution
- Context generation and delta queries

## Architecture

```
ellmos Architecture
====================

  LLM (Claude, Gemini, Ollama, ...)
    |
    v
  SKILL.md  (operating instructions for the LLM)
    |
    v
  BACH CLI / API  (bach.py)
    |
    +---> Handlers (109+)  ---> Database (bach.db, 142 tables)
    +---> Skills (932+)    ---> File System (markdown, templates)
    +---> Tools (373+)     ---> External Services (bridges)
    +---> Agents           ---> Other LLMs (swarm, orchestration)
    +---> SharedMemory     ---> USMC (cross-agent coordination)
    +---> Scheduler        ---> Automated workflows
```

## Documentation

| Document | Description |
|----------|-------------|
| [BACH README](https://github.com/lukisch/bach) | Full system documentation |
| [BACH README (German)](https://github.com/lukisch/bach/blob/main/README.de.md) | Deutsche Dokumentation |
| [Rinnsal README](https://github.com/lukisch/rinnsal) | Compact system documentation |
| [USMC README](https://github.com/lukisch/usmc) | Memory layer documentation |

## License

All ellmos projects are released under the **MIT License**.

## Links

- **GitHub:** [github.com/lukisch](https://github.com/lukisch)
- **Organization:** [github.com/ellmos-ai](https://github.com/ellmos-ai) *(coming soon)*
- **Issues:** Use the issue tracker of the respective project repository

---

*ellmos -- Extensive Large Language Model Operating Systems*
*The stream that unites everything.*
