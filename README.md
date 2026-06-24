<!-- ========== HEADER ========== -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,1a2a3a,01696f&height=160&section=header&text=Chris%20Grady&fontSize=48&fontColor=ffffff&fontAlignY=40&desc=Infrastructure%20Engineer%20%C2%B7%20AI%20Agent%20Builder%20%C2%B7%20Security%20Tooling&descAlignY=62&descSize=16" width="100%"/>

[![Website](https://img.shields.io/badge/cgfixit.com-01696f?style=for-the-badge&logo=safari&logoColor=white)](https://cgfixit.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/cgrady92)
[![Email](https://img.shields.io/badge/contact@cgfixit.com-333?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@cgfixit.com)
</div>

---

## Domain Clusters

Projects across backup & DR, security and detection tooling, local LLM/RAG, and Windows automation. They're grouped into clusters below. A few reuse each other across cluster lines — for example, the YARA rules that scan restore points also feed the prompt-injection filter in the RAG agent.

[Interactive domain map](https://mail.cgfixit.com/Export/z/knowledge-map/) — the diagram below is a static version of the same map.

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
                  CyClaw · soul drift detection
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
| [**CyClaw**](https://github.com/CGFixIT/CyClaw) | Offline-first RAG agent where the LangGraph topology enforces the security policy. Hybrid retrieval (ChromaDB + BM25+RRF), SHA-256 integrity checks on prompt/state (soul-drift detection), OWASP-aligned prompt sanitization, and an MCP server. Runs fully local for air-gapped or privacy-sensitive use. | `Python` `LangGraph` `ChromaDB` `FastAPI` `SQLite` |
| [**AzureAI-CopilotStudio-PersonalAgent-Instructions**](https://github.com/CGFixIT/AzureAI-CopilotStudio-PersonalAgent-Instructions) | System-instruction templates for enterprise AI agents: tiered source hierarchy, anti-hallucination safeguards, and reference patterns (including VeeamGPT). | `Azure OpenAI` `Copilot Studio` `Prompt Engineering` |

### Security / YARA Detection

| Repo | What it does | Stack |
|---|---|---|
| [**Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links**](https://github.com/CGFixIT/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links) | YARA ruleset + PowerShell scanner that detects Tor `.onion` C2 infrastructure, BTC/XMR ransomware payment addresses, and common command-and-control patterns inside Veeam restore points. Outputs SIEM-ready JSON and integrates with Secure Restore workflows. | `PowerShell` `YARA` `Veeam` `Forensics` |

### Backup & DR Operations

| Repo | What it does | Stack |
|---|---|---|
| [**sccm-veeam-proxy-patching**](https://github.com/CGFixIT/sccm-veeam-proxy-patching) | Graceful Veeam proxy drain during SCCM patch windows: WinRM service management, pre/post task sequencing, and exit code 3010 (reboot-pending) handling so patch reboots don't fail in-flight backup jobs. | `PowerShell` `SCCM` `VMware` `Veeam` |
| [**Veeam-HealthCheck-Simplifier**](https://github.com/CGFixIT/Veeam-HealthCheck-Simplifier) | Parses Veeam health-check CSV/JSON, generates PowerShell remediation actions, and sends notifications to Salesforce/Slack/Teams. | `Python` `Veeam` `Analytics` |

### Automation / Scripting

| Repo | What it does | Stack |
|---|---|---|
| [**PolyMarket_Mimic_Trader**](https://github.com/CGFixIT/PolyMarket_Mimic_Trader) | Autonomous bot that tails the highest-ROI wallets on Polymarket, mirrors their trades in real time, and enforces configurable bankroll, exposure, and stop-loss rules. Async event-driven engine polls the GraphQL API, ranks traders by a Sharpe-like score, executes mirrored orders, logs to Prometheus/Grafana, and writes transactions to an immutable SQLite ledger. Includes .env-based secrets handling, dry-run / back-test mode, and a financial-risk disclaimer. | `Python` `asyncio` `GraphQL` `SQLite` |
| [**Scrape-n-Email**](https://github.com/CGFixIT/Scrape-n-Email) | Scraper for news + job digests (RealClearPolitics headlines + Atlanta Craigslist sysadmin roles). MIME-safe email delivery, formula-safe CSV handling, cross-platform logging, and offline testability. | `Python` `BeautifulSoup` `SMTP` |

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
</p>

---

## Currently Building

- **CyClaw v1.7** — LangGraph topology rewrite, MCP server, OPA/Rego policy enforcement layer (active development)

---

<div align="center">
<sub>Atlanta, GA · Infrastructure & security engineering</sub>
</div>
