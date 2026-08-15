<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,1a2a3a,01696f&height=170&section=header&text=Chris%20Grady&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Infrastructure%20%E2%80%A2%20Security%20%E2%80%A2%20Applied%20AI&descAlignY=62&descSize=18" width="100%" alt="Chris Grady — Infrastructure, Security, and Applied AI" />

### I build secure automation and local AI systems for infrastructure that cannot afford to fail.

<p align="center">
<i>Systems / Solutions Engineer working across <b>data protection, Windows automation, detection engineering, and governed AI agents</b>.<br />
My projects connect production infrastructure experience with practical Python, PowerShell, RAG, and security engineering.</i>
</p>

<p align="center">
<a href="https://cgfixit.com"><img src="https://img.shields.io/badge/cgfixit.com-01696f?style=for-the-badge&logo=safari&logoColor=white&labelColor=0d1117" alt="Website" /></a>
<a href="https://linkedin.com/in/cgrady92"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0d1117" alt="LinkedIn" /></a>
<a href="mailto:contact@cgfixit.com"><img src="https://img.shields.io/badge/contact%40cgfixit.com-333333?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0d1117" alt="Email" /></a>
</p>

<p align="center">
<a href="https://o3mjwe6dliqf6.kimi.page/"><img src="https://img.shields.io/badge/%E2%96%B6%20Try%20CyClawOS-live%20demo-01696f?style=for-the-badge&labelColor=0d1117" alt="Try CyClawOS — live demo" /></a>
<a href="https://github.com/CGFixIT/CyClaw"><img src="https://img.shields.io/badge/CyClaw-source-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="CyClaw source" /></a>
</p>

</div>

---

<h2 align="center">Try It: CyClawOS</h2>
<p align="center"><i>Interactive CyClaw Demos</i></p>

<div align="center">

<a href="https://o3mjwe6dliqf6.kimi.page/"><img src="https://img.shields.io/badge/%E2%96%B6%20Launch%20CyClawOS-Kimi%20build-01696f?style=for-the-badge&labelColor=0d1117" alt="Launch CyClawOS — Kimi build" /></a>
&nbsp;
<a href="https://cyclaw-demo-cgrady92.grok.me"><img src="https://img.shields.io/badge/%E2%96%B6%20Launch%20Mirror-Grok%20build-1a2a3a?style=for-the-badge&labelColor=0d1117" alt="Launch mirror — Grok build" /></a>

<sub>Primary: <a href="https://o3mjwe6dliqf6.kimi.page/">o3mjwe6dliqf6.kimi.page</a> · short link <a href="https://bit.ly/CyClawDemo">bit.ly/CyClawDemo</a> — Mirror: <a href="https://cyclaw-demo-cgrady92.grok.me">cyclaw-demo-cgrady92.grok.me</a></sub>

</div>

<br />

**CyClawOS** is a browser-based desktop environment that puts the [CyClaw](https://github.com/CGFixIT/CyClaw) agent architecture behind a real interface. Instead of a chat box and a diagram, you get a simulated Linux workstation that boots, arms its guardrails, and lets you drive the agent's actual control surfaces: retrieval, the write gate, the soul file, and the audit log.

Two independently deployed builds of the same system, so the demo survives one host having a bad day.

```text
CyClawOS 2.0.0 (linux-x86_64)
Loading kernel modules .............. ok
Starting gate.py :8787 .............. ok
Soul + guardrails ................... armed
Starting desktop session ............
```

<h3 align="center">What you can actually poke at</h3>

| App | What it demonstrates |
|:---|:---|
| **CyClaw Terminal** | Full shell replica with `rag`, `soul`, `sync`, and `agentic` subcommands |
| **CyClaw Harness** | Chat console with per-request toggles for skills, tools, web, and GitHub |
| **CyClaw RAG Query** | Hybrid retrieval — ChromaDB dense vectors + BM25 sparse, fused with RRF, with sources and hit latency shown |
| **Guardrails** | Paste hostile input and watch the 33-pattern deny list evaluate it in the open |
| **CyClaw Agentic** | `agentic/fsconnect` allow-listed reads and gated writes; `agentic/sqlconnect` restricted to read-only `SELECT` |
| **Audit Logs / `audit.jsonl`** | Every tool call appended to a JSONL audit trail you can read back |
| **Soul File** | Human-gated governance directives — the part a prompt is not allowed to edit |
| **CyClaw Sync** | rclone/Dropbox corpus sync with dry-run before anything is written |
| **Metrics · Health Check · Config · Docs** | Retrieval latency, gate p95, index size, embedding dimension, live config |

The CyClaw tooling sits inside a complete desktop — file manager, text and code editors, Python runner, git client, SSH and network tools, and the usual accessories — because the point is showing governed agent tooling **in an operating environment**, not as an isolated widget.

The design decisions on display are the ones that matter in the real system:

- **Retrieval always runs before generation.** The LLM is the last node in the graph, not the first.
- **Writes are gated, reads are allow-listed, SQL is `SELECT`-only.** Denial is the default and it is visible.
- **Everything is auditable.** If a tool ran, there is a line in `audit.jsonl` saying so.

> [!NOTE]
> CyClawOS is a faithful browser-side simulation of the real agent's flows and interfaces — it runs entirely client-side with no live model calls or network access to your data. The production system it mirrors is [CyClaw](https://github.com/CGFixIT/CyClaw) (Python 3.12, LangGraph, ChromaDB, Ollama).

---

<h2 align="center">Domain Clusters</h2>

<p align="center">
<a href="https://mail.cgfixit.com/Export/z/knowledge-map/"><b>Interactive Domain Map</b></a> — the diagram below is a static version of the same map.
</p>

```
           Security / Detection / Programming
               YARA rules · Powershell
                Python · C2 · OWASP
                        │
            ── BRIDGE ──┤── BRIDGE ──
        YARA pre-restore│  YARA → prompt injection
        malware-aware DR│  pattern defense for LLMs
                        │
  Backup & DR    ───────┼─────── Local LLM / RAG
  Veeam VBR             │        LangGraph · ChromaDB
  Network Security      │        BM25+RRF · Ollama
Systems Architecture    │        offline-first
                        │
            ── BRIDGE ──┤── BRIDGE ──
VBR data → AI or SIEM   │  topology = policy enforcement
    remediation agents  │  Agentic compliance & governance
                        │
              AI Safety | Agent Governance
               CyClaw   · Agentic AI drift detection
      SHA-256 integrity · MCP server
                        │
              Automation / Sysadmin (substrate)
       PowerShell· SCCM · HCI · VMware
       Azure · AWS  · Edge · Hyper-V
```

---

<h2 align="center">What I Work On</h2>

- **Secure local AI:** offline-first RAG, agent governance, policy-enforced workflows, prompt-injection defenses, and MCP-based tooling.
- **Data protection and recovery:** Veeam operations, malware-aware restore workflows, health-check automation, and resilient infrastructure lifecycle management.
- **Detection engineering:** YARA rules, ransomware indicators, suspicious infrastructure detection, and SIEM-ready output.
- **Windows and platform automation:** PowerShell, Python, SCCM, WinRM, VMware, APIs, and operational tooling designed for real environments rather than immaculate demo laptops.

> [!IMPORTANT]
> **The common thread:** security policy should be enforced by system design, not merely requested in a prompt or buried in a runbook.

---

<h2 align="center">Featured Work</h2>

<h3 align="center"><a href="https://github.com/CGFixIT/CyClaw">CyClaw</a></h3>
<p align="center"><i>Governed, offline-first RAG agent</i></p>

<p align="center">
<code>Python 3.12</code> <code>LangGraph</code> <code>FastAPI</code> <code>ChromaDB</code> <code>BM25 + RRF</code> <code>SQLite</code> <code>pgvector</code> <code>MCP</code> <code>Ollama</code>
</p>

A local AI agent built around the principle that **architecture should enforce policy**. CyClaw uses a LangGraph state machine, hybrid retrieval, integrity checks, scoped tooling, and auditable execution to reduce reliance on prompt-only safeguards.

- **RAG-first retrieval** — retrieval runs before generation, every time.
- **Topology as policy** — the graph decides what is reachable; the prompt does not get a vote.
- **Scoped tools** — allow-listed filesystem reads, approval-gated writes, read-only SQL.
- **JSONL audit logging** and SHA-256 integrity checks over the corpus.

**Why it matters:** organizations need useful AI systems that can operate around sensitive data, constrained networks, and explicit governance requirements without quietly turning every control into a polite suggestion.

<p align="center">
<b>Try it:</b>
<a href="https://o3mjwe6dliqf6.kimi.page/">CyClawOS interactive demo</a> ·
<a href="https://cyclaw-demo-cgrady92.grok.me">mirror</a> ·
<a href="https://cgfixit.com/CyClaw">project page</a>
</p>

---

<h3 align="center"><a href="https://github.com/CGFixIT/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links">Veeam YARA Scanner</a></h3>
<p align="center"><i>Malware-aware recovery inspection</i></p>

<p align="center">
<code>PowerShell</code> <code>YARA</code> <code>Veeam</code> <code>JSON</code> <code>Forensics</code> <code>Detection Engineering</code>
</p>

PowerShell and YARA tooling for detecting `.onion` infrastructure, cryptocurrency payment indicators, and command-and-control patterns in recovery data, with structured output suitable for investigation and SIEM workflows.

---

<h3 align="center"><a href="https://github.com/CGFixIT/sccm-veeam-proxy-patching">SCCM Veeam Proxy Patching</a></h3>
<p align="center"><i>Safe infrastructure maintenance</i></p>

<p align="center">
<code>PowerShell</code> <code>SCCM</code> <code>WinRM</code> <code>VMware</code> <code>Veeam</code>
</p>

Coordinates Veeam proxy availability with SCCM patching so maintenance can proceed without casually rebooting infrastructure beneath active backup jobs, a surprisingly popular human pastime. Runs SCCM-integrated or standalone from VBR.

---

<h2 align="center">More Projects</h2>

| Project | Focus | Primary stack |
|:---|:---|:---|
| [**Insight Extractor**](https://github.com/CGFixIT/Insight_Extractor) | Turns long threads into structured notes for you or your agent — BERT + regex extraction with a dynamic keyword stemmer, aimed at threat-intel and OSINT pipelines. [Project page](https://cgfixit.com/ai) | `Python` `BERT` `Sentence-Transformers` `Pydantic` `NLP` |
| [**Veeam HealthCheck Simplifier**](https://github.com/CGFixIT/Veeam-HealthCheck-Simplifier) | Parses VBR health-check results from CSV/JSON, emits PowerShell remediation, and routes findings to Salesforce or Slack. | `Python` `Veeam` `PowerShell` `Automation` |
| [**Azure AI Agent Instructions**](https://github.com/CGFixIT/AzureAI-CopilotStudio-PersonalAgent-Instructions) | Production-tested enterprise agent instruction patterns covering source hierarchy, grounding, and hallucination resistance. | `Azure OpenAI` `Copilot Studio` `Prompt Engineering` |
| [**Windows / Linux / Docker Handbook**](https://github.com/CGFixIT/Windows-Linux--Docker-Handbook) | Admin one-liner cheat sheet spanning 2016–2025, published as a searchable web app. [Live app](https://cg-windows-admin-cmd-ps1-ref.pplx.app) · [GitHub Pages](https://cgfixit.github.io/Windows-Linux--Docker-Handbook/) | `HTML` `PowerShell` `Bash` `Docker` |
| [**PolyMarket Mimic Trader**](https://github.com/CGFixIT/PolyMarket_Mimic_Trader) | Event-driven research project: ranks top Polymarket traders, then applies deliberately conservative thresholds with risk controls, simulation, and ledgered execution. Paper mode only so far. | `Python` `asyncio` `GraphQL` `SQLite` |
| [**Scrape-n-Email**](https://github.com/CGFixIT/Scrape-n-Email) | Resilient scraping and daily digest delivery with testable parsing, formula-safe CSV handling, and offline tests. | `Python` `BeautifulSoup` `SMTP` |

<details>
<summary><strong>Earlier public work (archived)</strong></summary>

<br />

| Project | Notes |
|:---|:---|
| [**Blackjack**](https://github.com/CGFixIT/Blackjack) | Console casino blackjack with user accounts. `C++` |
| [**EMR System**](https://github.com/CGFixIT/EMR-System) | Dentist office medical record simulator with a Swing GUI. `Java` |

Kept public for history. Not maintained, and not representative of current work.

</details>

---

<h2 align="center">Engineering Approach</h2>

```text
production constraint
      ↓
explicit threat / failure model
      ↓
architecture-enforced controls
      ↓
auditable automation
      ↓
operator-friendly outcome
```

I tend to optimize for:

- **Local-first operation** where privacy, cost, latency, or network isolation matter.
- **Defense in depth** rather than a single magical control with an impressive acronym.
- **Dry-run modes, validation, logging, and rollback-aware workflows.**
- **Useful interfaces for operators**, not just technically correct code that demands its own priesthood.
- **Clear documentation and reproducibility** so projects can be evaluated beyond screenshots and claims.

---

<h2 align="center">Technology</h2>

<p align="center">
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white" alt="PowerShell" />
<img src="https://img.shields.io/badge/LangGraph-6C4AB6?style=flat-square" alt="LangGraph" />
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
<img src="https://img.shields.io/badge/ChromaDB-EA5A0C?style=flat-square" alt="ChromaDB" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" alt="SQLite" />
</p>

<p align="center">
<img src="https://img.shields.io/badge/YARA-8B0000?style=flat-square" alt="YARA" />
<img src="https://img.shields.io/badge/Veeam-00B336?style=flat-square" alt="Veeam" />
<img src="https://img.shields.io/badge/Azure_AI-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Azure AI" />
<img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white" alt="Ollama" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
<img src="https://img.shields.io/badge/VMware-607078?style=flat-square&logo=vmware&logoColor=white" alt="VMware" />
<img src="https://img.shields.io/badge/SCCM-0078D7?style=flat-square&logo=windows&logoColor=white" alt="SCCM" />
</p>

---

<details>
<summary><strong>How the project areas connect</strong></summary>

<br />

```text
                 Security / Detection
            YARA · ransomware indicators · OWASP
                         │
       malware-aware DR  │  injection-pattern defense
                         │
Data Protection ─────────┼───────── Local AI / RAG
Veeam · recovery         │          LangGraph · hybrid retrieval
proxy lifecycle          │          local models · MCP
                         │
      operational data   │  topology-enforced governance
                         │
                 Automation Layer
          Python · PowerShell · SCCM · WinRM · APIs
```

The projects are not separate hobby bins. Detection logic informs recovery inspection and AI input defenses; infrastructure telemetry informs automation; and governance patterns from agent systems influence how write-capable operational tools are scoped and audited.

[Open the interactive domain map](https://mail.cgfixit.com/Export/z/knowledge-map/)

</details>

---

<h2 align="center">Current Focus</h2>

- Expanding **CyClaw's governed agentic coding and local-model support**.
- Growing the **CyClawOS demo** so the governance surfaces — write gate, soul file, audit trail — can be evaluated by anyone with a browser.
- Improving policy enforcement, evaluation, observability, and offline deployment paths.
- Turning hard-won infrastructure and recovery patterns into reusable security automation.

<div align="center">

<br />

**Atlanta, GA · Infrastructure · Data Protection · Security · Applied AI**

<sub>Building systems that remain useful after the demo ends.</sub>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,1a2a3a,01696f&height=120&section=footer" width="100%" alt="" />

</div>
