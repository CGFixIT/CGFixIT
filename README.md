<!-- ========== HEADER ========== -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,1a2a3a,01696f&height=160&section=header&text=Chris%20Grady&fontSize=48&fontColor=ffffff&fontAlignY=40&desc=Infrastructure%20Engineer%20%C2%B7%20AI%20Agent%20Builder%20%C2%B7%20Security%20Tooling&descAlignY=62&descSize=16" width="100%"/>

[![Website](https://img.shields.io/badge/cgfixit.com-01696f?style=for-the-badge&logo=safari&logoColor=white)](https://cgfixit.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/cgrady92)
[![Email](https://img.shields.io/badge/contact@cgfixit.com-333?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@cgfixit.com)
</div>

---

## What is this for — My Domain Clusters

> My portfolio isn't a collection of random projects (well.. there is some) — it's a converging architecture.  
> The real differentiator lives **at the intersections**, not inside any single cluster.

> [Interactive domain map](https://mail.cgfixit.com/Export/z/knowledge-map/)
<hr>
> The diagram below is a quick visual for technical readers
<hr>

```
           Security / Detection
               YARA rules · PS1 scanner
               onion-link detection · OWASP
                        │
            ── BRIDGE ──┤── BRIDGE ──
        YARA pre-restore │  YARA → prompt injection
        malware-aware DR │  pattern defense for LLMs
                        │
  Backup & DR ───────┼─────── Local LLM / RAG
  Veeam VBR             │        LangGraph · ChromaDB
  proxy lifecycle       │        BM25+RRF · Ollama
  health-check ops      │        offline-first
                        │
            ── BRIDGE ──┤── BRIDGE ──
    VBR telemetry → AI  │  topology = policy enforcement
    remediation agents  │  soul governance · SQLite
                        │
              AI Safety / Agent Governance
                  PsyClaw · soul drift detection
                  SHA-256 integrity · MCP server
                        │
              Automation / Sysadmin (substrate)
              PowerShell · SCCM · WinRM · VMware
```

---

## Projects by Cluster

### AI Agents & Safety

| Repo | What it does | Stack |
|---|---|---|
| [**PsyClaw**](https://github.com/CGFixIT/PsyClaw) | Offline-first RAG agent with LangGraph topology acting as enforceable security policy. Hybrid retrieval (ChromaDB + BM25+RRF), SHA-256 soul drift detection, OWASP-aligned prompt sanitization, and MCP server. Built for memory sovereignty and prompt injection resistance in air-gapped or privacy-sensitive environments. | `Python` `LangGraph` `ChromaDB` `FastAPI` `SQLite` |
| [**AzureAI-CopilotStudio-PersonalAgent-Instructions**](https://github.com/CGFixIT/AzureAI-CopilotStudio-PersonalAgent-Instructions) | Production-tested system instructions for enterprise AI agents. Tiered source hierarchy, anti-hallucination safeguards, and reference implementation patterns (including VeeamGPT). Designed to make agent behavior predictable and auditable at scale. | `Azure OpenAI` `Copilot Studio` `Prompt Engineering` |

### Security / YARA Detection

| Repo | What it does | Stack |
|---|---|---|
| [**Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links**](https://github.com/CGFixIT/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links) | YARA ruleset + PowerShell scanner that detects Tor `.onion` C2 infrastructure, BTC/XMR ransomware payment addresses, and common command-and-control patterns inside Veeam restore points. Outputs SIEM-ready JSON and integrates with Secure Restore workflows — turns blind restores into malware-aware, auditable operations. | `PowerShell` `YARA` `Veeam` `Forensics` |

### Backup & DR Operations

| Repo | What it does | Stack |
|---|---|---|
| [**sccm-veeam-proxy-patching**](https://github.com/CGFixIT/sccm-veeam-proxy-patching) | Graceful Veeam proxy drain during SCCM patch windows. WinRM service management, pre/post task sequencing, and exit code 3010 handling. Prevents backup job failures and data protection gaps during routine maintenance windows. | `PowerShell` `SCCM` `VMware` `Veeam` |
| [**Veeam-HealthCheck-Simplifier**](https://github.com/CGFixIT/Veeam-HealthCheck-Simplifier) | CSV/JSON Veeam health check analyzer that produces PowerShell remediation actions plus direct Salesforce/Slack/Teams notifications. Turns hours of manual review into automated, actionable alerts for operations teams. | `Python` `Veeam` `Analytics` |

### Automation / Scripting

| Repo | What it does | Stack |
|---|---|---|
| [**PolyMarket_Mimic_Trader**](https://github.com/CGFixIT/PolyMarket_Mimic_Trader) | Autonomous bot that tails the highest-ROI wallets on Polymarket, copies their trades in real time, and enforces configurable bankroll, exposure and stop-loss rules. Async, event-driven engine polls the GraphQL API, ranks traders by Sharpe-like score, executes mirrored orders, logs to Prometheus/Grafana and rolls transactions to an immutable SQLite ledger. Ships with .env-based secrets handling, dry-run / back-test mode, and a loud financial-risk disclaimer. | `Python` `asyncio` `GraphQL` `SQLite` |
| [**Scrape-n-Email**](https://github.com/CGFixIT/Scrape-n-Email) | Lightweight, reliable scraper for news + job digests (RealClearPolitics headlines + Atlanta Craigslist sysadmin roles). MIME-safe email delivery, formula-safe CSV handling, cross-platform logging, and offline testability. Keeps research and opportunity pipelines clean without manual busywork. | `Python` `BeautifulSoup` `SMTP` |

---

## The Core Thesis

> *"Backups are operational memory and last-resort truth stores — backup infrastructure is a trustworthy-AI primitive."*

This means:
- **Veeam** is not just a backup tool — it's a **ground-truth substrate** for AI-assisted recovery decisions.
- **YARA** is not just malware detection — it's the **prompt injection defense layer** for AI agents (see `sanitizer.py` in PsyClaw → next evolution: `yara-prompt-guard`).
- **PsyClaw** is not just orchestration — it's **security policy as code** (LangGraph Topology = enforcement).

---

## Stack at a Glance

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white"/>
<img src="https://img.shields.io/badge/LangGraph-blueviolet?style=flat-square"/>
<img src="https://img.shields.io/badge/ChromaDB-orange?style=flat-square"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/YARA-darkred?style=flat-square"/>
<img src="https://img.shields.io/badge/Veeam-01a982?style=flat-square"/>
<img src="https://img.shields.io/badge/Azure_OpenAI-0089D6?style=flat-square&logo=microsoftazure&logoColor=white"/>
<img src="https://img.shields.io/badge/LM_Studio-607078?style=flat-square"/>
<img src="https://img.shields.io/badge/VMware-607078?style=flat-square&logo=vmware&logoColor=white"/>
<img src="https://img.shields.io/badge/SCCM-0078D7?style=flat-square&logo=windows&logoColor=white"/>
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white"/>
</p>

---

## Currently Building

- **PsyClaw v1.3** — LangGraph topology rewrite, MCP server, OPA/Rego policy enforcement layer (active development)

---

<div align="center">
<sub>Atlanta, GA · Systems Engineer → Infrastructure Engineer → AI Agent Builder · Infrastructure / security engineering roles</sub>
</div>
