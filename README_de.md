<p align="center">
  <img src="ellmos-logo.jpg" alt="ellmos Logo" width="400">
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

## Hier anfangen

| Wenn Sie suchen... | Beginnen Sie mit | Warum |
|---|---|---|
| Ein vollständiges persönliches LLM-Betriebssystem mit GUI, Skills, Scheduler, Bridges und Multi-Agenten-Workflows | [BACH](https://github.com/ellmos-ai/bach) | Größtes ellmos-System und der zentrale Integrationspunkt |
| Eine leichtgewichtige Python-Infrastrukturschicht für Gedächtnis, Tasks, Connectors und Ketten | [Rinnsal](https://github.com/ellmos-ai/rinnsal) | Kleines, local-first Fundament mit minimalen Abhängigkeiten |
| Ein minimales LLM-natives SQLite-Experiment | [gardener](https://github.com/ellmos-ai/gardener) | Ein-Tabellen-Substrat für einfache Agenten |
| Geteiltes Gedächtnis, Modell-Routing, Ketten oder parallele Agenten-Muster | [USMC](https://github.com/ellmos-ai/usmc), [clutch](https://github.com/ellmos-ai/clutch), [MarbleRun](https://github.com/ellmos-ai/MarbleRun), [swarm-ai](https://github.com/ellmos-ai/swarm-ai) | Eigenständige Module, kombinierbar mit jeder OS-Stufe |
| MCP-Server für Claude Code, Cursor oder andere KI-IDEs | [CodeCommander](https://github.com/ellmos-ai/ellmos-codecommander-mcp), [FileCommander](https://github.com/ellmos-ai/ellmos-filecommander-mcp), [n8n Manager](https://github.com/ellmos-ai/n8n-manager-mcp), [ControlCenter](https://github.com/ellmos-ai/ellmos-controlcenter-mcp), [Homebase](https://github.com/ellmos-ai/ellmos-homebase-mcp), [ServerCommander](https://github.com/ellmos-ai/ellmos-servercommander-mcp) | Tool-Server für Code, Dateien, Workflows, lokalen Zustand und lokale Steuerungsebenen |

---

## Welches OS passt zu mir?

| Frage | BACH | Rinnsal | gardener |
|----------|------|---------|----------|
| Ich will ein vollausgestattetes Agenten-OS mit GUI, Skills und Multi-Agenten-Orchestrierung | **Ja** | | |
| Ich will leichtgewichtige LLM-Infrastruktur ohne Abhängigkeiten | | **Ja** | |
| Ich will das einfachstmögliche LLM-native OS (1 Tabelle, 4 Funktionen) | | | **Ja** |
| Ich brauche Telegram-/E-Mail-/WhatsApp-Connectors | **Ja** | **Ja** | Geplant |
| Ich will mich zur Laufzeit selbst um neue Skills erweitern | **Ja** | | |
| Ich will minimalen Umfang (~2k Zeilen) | | **Ja** | **Ja** |

---

## Die ellmos-Familie

### BACH -- Der Strom, der alles vereint

Das vollständige LLM-Betriebssystem. 113+ Handler, 550+ Werkzeuge, 1870+ Skills, 71 Workflow-Vorlagen, 11 Boss-Agenten mit 22 Experten, PySide6-Desktop-GUI, Scheduler, Bridge-System und Selbsterweiterung über `bach skills create`.

```bash
git clone https://github.com/ellmos-ai/bach.git
cd bach && pip install -r requirements.txt
python system/setup.py
python bach.py --startup
```

**[Vollständige BACH-Dokumentation](https://github.com/ellmos-ai/bach)**

### Rinnsal -- Das Rinnsal

Leichtgewichtige LLM-Infrastruktur: Gedächtnis, Tasks, Connectors, Ketten. Keine externen Abhängigkeiten. Alles, was BACH konzeptionell tut, in rund 2.000 Zeilen -- für Entwickler, die ihren eigenen Agenten darauf aufbauen wollen.

```bash
git clone https://github.com/ellmos-ai/rinnsal.git
cd rinnsal && pip install -r requirements.txt
```

**[Vollständige Rinnsal-Dokumentation](https://github.com/ellmos-ai/rinnsal)**

### gardener -- Der Zen-Garten

LLM-natives OS: eine `everything`-Tabelle, 4 Funktionen, FTS5-Volltextsuche -- verteilt auf zwei Datenbanken (`gardener.db` für Systemwissen, `user.db` für Ihre Daten), die eine Abfrage gemeinsam durchsucht. Alles ist durchsuchbar. Das LLM *ist* der Agent -- gardener liefert nur den Boden.

```bash
git clone https://github.com/ellmos-ai/gardener.git
cd gardener && pip install -r requirements.txt
```

**[Vollständige gardener-Dokumentation](https://github.com/ellmos-ai/gardener)**

---

## Architektur: 3 OS-Schichten + steckbare Module

```
+-------------------------------------------------+
|              Waehle deine OS-Schicht            |
|                                                 |
|   BACH (voll)   Rinnsal (leicht) gardener (min) |
|   +---------+   +------------+   +----------+  |
|   | 1870+   |   | Keine Deps |   | 1 Tabelle|  |
|   | Skills  |   | Connectors |   | 4 Funkt. |  |
|   | 11 Boss |   | Ketten     |   | FTS5     |  |
|   | Agenten |   | Events     |   | = Suche  |  |
|   +----+----+   +-----+------+   +-----+----+  |
|        +---------------+----------------+       |
|                        |                        |
|        +---------------+---------------+        |
|        |    Steckbare Module           |        |
|        |                               |        |
|        |  USMC      -- Gedaechtnis     |        |
|        |  clutch    -- Modell-Routing  |        |
|        |  MarbleRun -- Agenten-Ketten  |        |
|        |  swarm-ai  -- parallele LLMs  |        |
|        +-------------------------------+        |
+-------------------------------------------------+
```

### Detaillierter Vergleich

| | **BACH** | **Rinnsal** | **gardener** |
|---|---|---|---|
| **Philosophie** | Maximalistisch: alles integriert | Leichtgewichtig: keine Abhängigkeiten | Minimalistisch: 1 Tabelle, 4 Funktionen |
| **Datenbank** | SQLite (210+ Tabellen) | SQLite (strukturiert) | SQLite (1 Tabelle `everything` + FTS5, über 2 Dateien) |
| **Gedächtnis** | 6 Gedächtnistypen mit Decay, Konflikterkennung, Konsolidierung | Facts/Notes/Lessons/Sessions | Vereinheitlicht (memo/lesson/recall + Decay) |
| **Tasks** | Vollständiges GTD (Priorität, Frist, Tags) | Priorität + Status + Agentenzuweisung | type='task' in `everything` |
| **Werkzeuge** | 550+ spezialisierte Werkzeuge | CLI-Befehle | 6 Bridge- und Skin-Werkzeuge (erweiterbar) |
| **Skills/Agenten** | 1870+ Skills, 11 Boss-Agenten, 22 Experten | Keine | Keine (das LLM ist der Agent) |
| **Connectors** | Telegram, E-Mail, WhatsApp | Telegram, Discord, Home Assistant | Geplant (v0.2+) |
| **GUI** | PySide6 Desktop + Web | Nur CLI | Nur CLI |
| **Selbsterweiterung** | `bach skills create` | Nein | Nein |
| **Codebasis** | ~50.000+ Zeilen | ~2.000 Zeilen | ~1.600 Zeilen |
| **Am besten für** | Power-User, alles aus einer Hand | Entwickler, die leichte Infrastruktur wollen | Minimalisten, LLM-native Experimente |

---

## Steckbare Module

Diese Module fügen sich in jedes ellmos-OS ein -- oder laufen eigenständig:

| Modul | Zweck | Kernmerkmal | Repository |
|---|---|---|---|
| **USMC** | Agentenübergreifendes gemeinsames Gedächtnis | Konfliktauflösung nach Konfidenz, Änderungsverfolgung | [ellmos-ai/usmc](https://github.com/ellmos-ai/usmc) |
| **clutch** | Anbieterneutrales Modell-Routing | Lernt selbst, welches Modell zu welcher Aufgabe passt; Budgetzonen | [ellmos-ai/clutch](https://github.com/ellmos-ai/clutch) |
| **MarbleRun** | Ketten-Orchestrierung | Autonome Mehrrunden-Agentenschleifen mit Kontextübergabe | [ellmos-ai/MarbleRun](https://github.com/ellmos-ai/MarbleRun) |
| **swarm-ai** | Parallele LLM-Koordination | 5 Muster: Epstein, Hierarchie, Stigmergie, Konsens, Spezialist | [ellmos-ai/swarm-ai](https://github.com/ellmos-ai/swarm-ai) |

> **gardener hat zwei Rollen, und beide sind aktuell.** Eigenständig betrieben ist es die minimale
> OS-Stufe von oben: eine Tabelle, vier Funktionen, FTS5-Suche. In die **.MEMORY-Säule** eingebaut
> ist es der organische quellenübergreifende Index neben [usmc](https://github.com/ellmos-ai/usmc)
> (der kuratierten Fassade) und [taskplan](https://github.com/ellmos-ai/taskplan) (Task-Zustand).
> Welche Rolle gilt, hängt vom Einsatz ab -- siehe das
> [Organisationsprofil](https://github.com/ellmos-ai) für die Säulenansicht.

---

## MCP-Server

ellmos stellt [Model-Context-Protocol](https://modelcontextprotocol.io/)-Server für die Einbindung in Claude Code, Cursor und andere KI-gestützte IDEs bereit:

| Server | Werkzeuge | Beschreibung | Installation |
|--------|-------|-------------|---------|
| **[CodeCommander](https://github.com/ellmos-ai/ellmos-codecommander-mcp)** | 22 | Code-Analyse, Refactoring, Import-Verwaltung, JSON-/Encoding-Reparatur | `npm i -g ellmos-codecommander-mcp` |
| **[FileCommander](https://github.com/ellmos-ai/ellmos-filecommander-mcp)** | 46 | Dateiverwaltung, Batch-Operationen, Prozesssteuerung, asynchrone Suche, Cloud-Lock-Prüfung | `npm i -g ellmos-filecommander-mcp` |
| **[Clatcher](https://github.com/ellmos-ai/ellmos-clatcher-mcp)** | 12 | Dateireparatur, Formatkonvertierung, Duplikaterkennung, Batch-Operationen | `npm i -g ellmos-clatcher-mcp` |
| **[n8n Manager](https://github.com/ellmos-ai/n8n-manager-mcp)** | 18 | n8n-Workflows anlegen, aktualisieren, sichern und verwalten | `npm i -g n8n-manager-mcp` |
| **[ControlCenter](https://github.com/ellmos-ai/ellmos-controlcenter-mcp)** | 20 | Alpha-Steuerungsebene für lokale MCP-Server, Claude-Profile, Policy-Audits | `npm i -g ellmos-controlcenter-mcp` |
| **[Homebase](https://github.com/ellmos-ai/ellmos-homebase-mcp)** | 45 | Alpha-MCP-Server für lokales LLM-Gedächtnis, Wissen, Zustand, Routing, Tests und Orchestrierung | siehe Repo-README |
| **[ServerCommander](https://github.com/ellmos-ai/ellmos-servercommander-mcp)** | 8 | Alpha-MCP-Server für Deploy-Trockenläufe, Mail-Status, Log-Analyse und Server-Health-Checks | siehe Repo-README |
| **[Blender-Use](https://github.com/ellmos-ai/ellmos-blender-use-mcp)** | 3 | Headless-Blender-Asset-QA: Hintergrundrendering, FBX-Reimport-Prüfung, Skriptausführung | `npm i -g ellmos-blender-use-mcp` |
| **[open-compute](https://github.com/ellmos-ai/open-compute-mcp)** | 10 | Computer-Use über MCP: Bildschirmaufnahme, semantische UI-Adressierung via Windows UIA, kanonische Aktionen | `npm i -g open-compute-mcp` |

---

## Weitere Projekte

| Projekt | Beschreibung | Repository |
|---|---|---|
| **skills** | Steckbare Skill-Bibliothek (Entwicklung, Forschung, Bildung, Infrastruktur) | [ellmos-ai/skills](https://github.com/ellmos-ai/skills) |
| **n8n Workflow Manager** | Eigenständige GUI zur Erstellung von n8n-Workflows | [ellmos-ai/n8n-workflow-manager](https://github.com/ellmos-ai/n8n-workflow-manager) |
| **ellmos-stack** | Selbst gehosteter KI-Stack (Docker, Ollama, n8n, Gedächtnis, Wissensbasis) | [ellmos-ai/ellmos-stack](https://github.com/ellmos-ai/ellmos-stack) |
| **ellmos-tests** | OS-übergreifende Testsuite und Benchmark-Berichte | [ellmos-ai/ellmos-tests](https://github.com/ellmos-ai/ellmos-tests) |
| **stacks** | Katalog und gemeinsames Manifest-Schema für jeden Stack der Familie | [ellmos-ai/stacks](https://github.com/ellmos-ai/stacks) |
| **agent-ops-stack** | Manifestgetriebene Komposition des lokalen Agent-Ops-Ökosystems | [ellmos-ai/agent-ops-stack](https://github.com/ellmos-ai/agent-ops-stack) |
| **connectors** | Portable Messaging-Connectors: Telegram, Discord, Signal, WhatsApp, Home Assistant, Webhook | [ellmos-ai/connectors](https://github.com/ellmos-ai/connectors) |
| **open-compute** | Modellneutraler Computer-Use-Kern für Claude, OpenAI CUA und Mock-Backends | [ellmos-ai/open-compute](https://github.com/ellmos-ai/open-compute) |
| **web-scraper** | Eigenständiger Web-Scraper mit SSRF-Schutz, aus BACH herausgelöst | [ellmos-ai/web-scraper](https://github.com/ellmos-ai/web-scraper) |
| **taskplan** | Deterministische Task-Auswahl, damit sich das Backlog nicht verstecken kann | [ellmos-ai/taskplan](https://github.com/ellmos-ai/taskplan) |
| **anonymizer** | Local-first Dokumenten-Pseudonymisierung mit fail-closed NER | [ellmos-ai/anonymizer](https://github.com/ellmos-ai/anonymizer) |
| **report-forge** | Domänenneutraler Kern für anonymisierbare Report-Pipelines | [ellmos-ai/report-forge](https://github.com/ellmos-ai/report-forge) |
| **project-docs-template** | Agentenfertige Projektdokumentations-Vorlage (START/STATE/TODO/DONE) | [ellmos-ai/project-docs-template](https://github.com/ellmos-ai/project-docs-template) |
| **clirec** | Menschenlesbare GUI-Demonstrationsaufzeichnungen für CLI- und Agenten-Workflows | [ellmos-ai/clirec](https://github.com/ellmos-ai/clirec) |
| **ai-media-editor** | Lokale KI-Bearbeitung für Video, Audio und Podcasts mit lokaler Transkription | [ellmos-ai/ai-media-editor](https://github.com/ellmos-ai/ai-media-editor) |
| **law-checker** | Quellenbelegte juristische Erstorientierung zum deutschen Recht | [ellmos-ai/law-checker](https://github.com/ellmos-ai/law-checker) |
| **steuer-assistent** | Offline-first Arbeitsblatt für Werbungskosten von Arbeitnehmern | [ellmos-ai/steuer-assistent](https://github.com/ellmos-ai/steuer-assistent) |
| **worksheet-generator** | ICF-orientierte Arbeitsblätter für pädagogische und therapeutische Arbeit | [ellmos-ai/worksheet-generator](https://github.com/ellmos-ai/worksheet-generator) |
| **build-your-users-mind** | Theory of Mind pro Nutzer: ein Entscheidungs-Avatar aus Interaktionsprotokollen | [ellmos-ai/build-your-users-mind](https://github.com/ellmos-ai/build-your-users-mind) |

---

## Verwandte Organisationen

`ellmos-ai` ist der KI-Infrastrukturteil einer größeren Familie local-first Projekte. Alle vier Organisationen unten verweisen bereits hierher; dies ist der Weg zurück.

| Organisation | Was dort liegt | Warum das hier zählt |
|---|---|---|
| **[open-bricks](https://github.com/open-bricks)** | Dachprofil für die gesamte Familie | Einstieg, wenn Sie die Desktop-, Dokumenten-, Forschungs- und Civic-Tech-Projekte neben der KI-Infrastruktur sehen wollen |
| **[dev-bricks](https://github.com/dev-bricks)** | Entwickler- und Multi-Agenten-Werkzeuge: [lock-master](https://github.com/dev-bricks/lock-master), [ticket-master](https://github.com/dev-bricks/ticket-master), [sync-master](https://github.com/dev-bricks/sync-master) | [agent-ops-stack](https://github.com/ellmos-ai/agent-ops-stack) setzt genau diese drei als Koordinationsschicht zusammen -- Dateisperren, Ticket-Routing und rechnerübergreifender Sync -- und jedes läuft auch eigenständig |
| **[file-bricks](https://github.com/file-bricks)** | Local-first Desktop-Werkzeuge für Dateien, Prompts und Wissensarbeit: [knowledgedigest](https://github.com/file-bricks/knowledgedigest), [promptboard](https://github.com/file-bricks/promptboard) | [ellmos-stack](https://github.com/ellmos-ai/ellmos-stack) nutzt KnowledgeDigest als Dokumentensuchschicht |
| **[doc-bricks](https://github.com/doc-bricks)** | Dokumenten-, Mail-, Literatur- und Notizwerkzeuge: [llm-note](https://github.com/doc-bricks/llm-note) | llm-note wurde aus BACHs Notizbuch-Mustern herausgelöst und ist eigenständig als Agenten-Notizwerkzeug nutzbar |

---

## Erste Schritte

1. **OS-Stufe wählen** anhand der Vergleichstabelle oben
2. **Klonen und installieren** mit den Schnellstart-Befehlen
3. **Optional Module ergänzen** (USMC für gemeinsames Gedächtnis, clutch für Modell-Routing usw.)
4. **MCP-Server einbinden** für die IDE-Integration: `npm i -g ellmos-codecommander-mcp ellmos-filecommander-mcp`

Alle Projekte: **Python 3.10+** | **SQLite** | **MIT-Lizenz** | **keine oder minimale Abhängigkeiten**

---

## Suche und Abgrenzung

ellmos ist die local-first LLM-Betriebssystemfamilie von `ellmos-ai`. Es ist nicht Eclipse LMOS, AllenAI OLMo, ELMo-Embeddings, Elmo Software oder eine gehostete Agentenplattform. Nützliche Suchbegriffe:

- `ellmos-ai ellmos local-first LLM operating system`
- `ellmos BACH Rinnsal gardener SQLite agent OS`
- `ellmos MCP CodeCommander FileCommander n8n Manager`
- `local-first LLM OS SQLite memory skills MCP`
- `Claude Code MCP local filesystem code analysis ellmos`
- `ellmos-ai ellmos canonical LLM OS namespace`

Der kanonische GitHub-Namensraum ist `ellmos-ai`. Ältere Suchindex-Auszüge zeigen unter Umständen noch `lukisch/ellmos` oder alte `bach-*`-Paketnamen; für neue Installationen gelten die `ellmos-ai/*`-Repositories und die aktuellen `ellmos-*`-MCP-Paketnamen.

Für automatisierte Indexierung und KI-Assistenten siehe [`llms.txt`](llms.txt).

---

## Lizenz

Alle ellmos-Projekte stehen unter der [MIT-Lizenz](LICENSE).

## Links

- **Organisation:** [github.com/ellmos-ai](https://github.com/ellmos-ai)
- **Autor:** [Lukas Geiger](https://github.com/lukisch)

---

*ellmos -- Extra Large Language Model Operating Systems*
*Der Strom, der alles vereint.*
