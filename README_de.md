<p align="center">
  <img src="ellmos-logo.jpg" alt="ellmos logo" width="400">
</p>

# ellmos -- Extra Large Language Model Operating Systems

*Von der Quelle zum Strom -- LLM-Betriebssysteme im Fluss.*

[English](README.md) | **Deutsch**

![License](https://img.shields.io/badge/Lizenz-MIT-green)
![Status](https://img.shields.io/badge/Status-Aktiv-brightgreen)
![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![SQLite](https://img.shields.io/badge/Datenbank-SQLite-003B57?logo=sqlite)
![LLM-Ready](https://img.shields.io/badge/LLM-Ready-blueviolet?logo=openai)
![Local-First](https://img.shields.io/badge/Architektur-Local--First-informational)

**ellmos** (XLLM-OS) ist eine Local-First-Familie textbasierter Betriebssysteme für Large Language Models: Agenten-Gedächtnis, Aufgabenstatus, MCP-Tools, Skills, Connector-Bridges, Modell-Routing und Multi-Agenten-Orchestrierung in schlanken, SQLite-gestützten Projekten. Entwickelt für Menschen, die eine transparente, lokal ausführbare und erweiterbare KI-Betriebsschicht ohne Cloud-Zwang bevorzugen.

> [!NOTE]
> **Maschinenlesbarer Index**: Für KI-Agenten, LLM-Tool-Aufrufer und automatisierte Indexierungs-Systeme steht ein vollständiges Kontext-Verzeichnis in [`llms.txt`](llms.txt) bereit.

> **Direktlinks:** [Organisation](https://github.com/ellmos-ai) | [BACH](https://github.com/ellmos-ai/bach) | [Rinnsal](https://github.com/ellmos-ai/rinnsal) | [gardener](https://github.com/ellmos-ai/gardener) | [llms.txt](llms.txt)

---

## Hier starten

| Wenn du folgendes suchst... | Starte mit | Warum |
|---|---|---|
| Ein vollständiges persönliches LLM-Betriebssystem mit GUI, Skills, Scheduler, Bridges und Multi-Agenten-Workflows | [BACH](https://github.com/ellmos-ai/bach) | Das größte ellmos-System und der Haupt-Integrationspunkt |
| Eine leichtgewichtige Python-Infrastrukturschicht für Gedächtnis, Aufgaben, Connectoren und Ketten | [Rinnsal](https://github.com/ellmos-ai/rinnsal) | Kleine, abgleitbare Local-First-Basis ohne schwere Abhängigkeiten |
| Ein minimales LLM-natives SQLite-Experiment | [gardener](https://github.com/ellmos-ai/gardener) | Ein-Tabellen-Betriebssubstrat für einfache Agenten |
| Geteiltes Gedächtnis, Modell-Routing, Ketten oder parallele Agenten-Muster | [USMC](https://github.com/ellmos-ai/usmc), [clutch](https://github.com/ellmos-ai/clutch), [MarbleRun](https://github.com/ellmos-ai/MarbleRun), [swarm-ai](https://github.com/ellmos-ai/swarm-ai) | Eigenständige Bausteine, die mit jeder OS-Stufe kombiniert werden können |
| MCP-Server für Claude Code, Cursor oder andere KI-IDEs | [CodeCommander](https://github.com/ellmos-ai/ellmos-codecommander-mcp), [FileCommander](https://github.com/ellmos-ai/ellmos-filecommander-mcp), [n8n Manager](https://github.com/ellmos-ai/n8n-manager-mcp), [ControlCenter](https://github.com/ellmos-ai/ellmos-controlcenter-mcp), [Homebase](https://github.com/ellmos-ai/ellmos-homebase-mcp), [ServerCommander](https://github.com/ellmos-ai/ellmos-servercommander-mcp) | Tool-Server für Code, Dateien, Workflows, lokalen Zustand und Kontrollarchitektur |

---

## Welches OS passt zu mir?

| Frage | BACH | Rinnsal | gardener |
|----------|------|---------|----------|
| Ich möchte ein vollwertiges Agenten-OS mit GUI, Skills und Multi-Agenten-Orchestrierung | **Ja** | | |
| Ich möchte eine minimale LLM-Infrastruktur ohne externe Abhängigkeiten | | **Ja** | |
| Ich möchte das einfachst mögliche LLM-native OS (1 Tabelle, 4 Funktionen) | | | **Ja** |
| Ich benötige Telegram/E-Mail/WhatsApp-Anbindungen | **Ja** | **Ja** | Geplant |
| Ich möchte das System zur Laufzeit selbst mit neuen Skills erweitern | **Ja** | | |
| Ich bevorzugen einen minimalen Code-Fußabdruck (~2k Zeilen) | | **Ja** | **Ja** |

---

## Architektur: 3 OS-Stufen + Modularer Aufbau

```
+-------------------------------------------------+
|            Wähle deine OS-Stufe                 |
|                                                 |
|   BACH (voll)   Rinnsal (leicht) gardener (min) |
|   +---------+   +------------+   +----------+  |
|   | 932     |   | Zero deps  |   | 1 Table  |  |
|   | Skills  |   | Connectors |   | 4 Funcs  |  |
|   | 5 Boss  |   | Chains     |   | FTS5     |  |
|   | Agenten |   | Events     |   | = Search |  |
|   +----+----+   +-----+------+   +-----+----+  |
|        +---------------+----------------+       |
|                        |                        |
|        +---------------+---------------+        |
|        |     Steckbare Module          |        |
|        |                               |        |
|        |  USMC      -- Shared Memory   |        |
|        |  clutch    -- Model Routing   |        |
|        |  MarbleRun -- Agent Chains    |        |
|        |  swarm-ai  -- Parallel LLMs   |        |
|        +-------------------------------+        |
+-------------------------------------------------+
```

---

## Lizenz & Links

- **Lizenz:** [MIT License](LICENSE)
- **Organisation:** [github.com/ellmos-ai](https://github.com/ellmos-ai)
- **Autor:** [Lukas Geiger](https://github.com/lukisch)

---

*ellmos -- Extra Large Language Model Operating Systems*
*Der Strom, der alles verbindet.*
