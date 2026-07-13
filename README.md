<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,1a2a3a,01696f&height=170&section=header&text=Chris%20Grady&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Infrastructure%20%E2%80%A2%20Security%20%E2%80%A2%20Applied%20AI&descAlignY=62&descSize=18" width="100%" alt="Chris Grady — Infrastructure, Security, and Applied AI" />

### I build secure automation and local AI systems for infrastructure that cannot afford to fail.

Systems / Solutions Engineer working across **data protection, Windows automation, detection engineering, and governed AI agents**. My projects connect production infrastructure experience with practical Python, PowerShell, RAG, and security engineering.

[![Website](https://img.shields.io/badge/cgfixit.com-01696f?style=for-the-badge&logo=safari&logoColor=white)](https://cgfixit.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/cgrady92)
[![Email](https://img.shields.io/badge/contact%40cgfixit.com-333333?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@cgfixit.com)
</div>

---


<center>[<a href="https://mail.cgfixit.com/Export/z/knowledge-map/">Interactive Domain Map</a>] - the diagram below is a static version of the same map.

---

<h3>## Domain Clusters</center></h3>

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
</div>

---

## What I Work On

- **Secure local AI:** offline-first RAG, agent governance, policy-enforced workflows, prompt-injection defenses, and MCP-based tooling.
- **Data protection and recovery:** Veeam operations, malware-aware restore workflows, health-check automation, and resilient infrastructure lifecycle management.
- **Detection engineering:** YARA rules, ransomware indicators, suspicious infrastructure detection, and SIEM-ready output.
- **Windows and platform automation:** PowerShell, Python, SCCM, WinRM, VMware, APIs, and operational tooling designed for real environments rather than immaculate demo laptops.

> **The common thread:** security policy should be enforced by system design, not merely requested in a prompt or buried in a runbook.

---

## Featured Work

### [CyClaw](https://github.com/CGFixIT/CyClaw) · Governed, offline-first RAG agent

A local AI agent built around the principle that **architecture should enforce policy**. CyClaw uses LangGraph topology, hybrid retrieval, integrity checks, scoped tooling, and auditable execution to reduce reliance on prompt-only safeguards.

`Python` `LangGraph` `FastAPI` `ChromaDB` `BM25 + RRF` `SQLite` `MCP` `Local LLMs`

**Why it matters:** organizations need useful AI systems that can operate around sensitive data, constrained networks, and explicit governance requirements without quietly turning every control into a polite suggestion.

---

### [Veeam YARA Scanner](https://github.com/CGFixIT/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links) · Malware-aware recovery inspection

PowerShell and YARA tooling for detecting `.onion` infrastructure, cryptocurrency payment indicators, and command-and-control patterns in recovery data, with structured output suitable for investigation and SIEM workflows.

`PowerShell` `YARA` `Veeam` `JSON` `Forensics` `Detection Engineering`

---

### [SCCM Veeam Proxy Patching](https://github.com/CGFixIT/sccm-veeam-proxy-patching) · Safe infrastructure maintenance

Coordinates Veeam proxy availability with SCCM patching so maintenance can proceed without casually rebooting infrastructure beneath active backup jobs, a surprisingly popular human pastime.

`PowerShell` `SCCM` `WinRM` `VMware` `Veeam`

---

## More Projects

| Project | Focus | Primary stack |
|---|---|---|
| [**Veeam HealthCheck Simplifier**](https://github.com/CGFixIT/Veeam-HealthCheck-Simplifier) | Parses health-check results, identifies remediation work, and streamlines operational follow-up. | `Python` `Veeam` `Automation` |
| [**Azure AI Agent Instructions**](https://github.com/CGFixIT/AzureAI-CopilotStudio-PersonalAgent-Instructions) | Enterprise agent instruction patterns covering source hierarchy, grounding, and hallucination resistance. | `Azure OpenAI` `Copilot Studio` |
| [**Insight Extractor**](https://github.com/CGFixIT/Insight_Extractor) | Extracts structured findings, themes, and actionable insights from large text inputs. | `Python` `NLP` `Automation` |
| [**PolyMarket Mimic Trader**](https://github.com/CGFixIT/PolyMarket_Mimic_Trader) | Event-driven research project for trader ranking, risk controls, simulation, and ledgered execution. | `Python` `asyncio` `GraphQL` `SQLite` |
| [**Scrape-n-Email**](https://github.com/CGFixIT/Scrape-n-Email) | Resilient scraping and digest delivery with testable parsing and safer CSV/email handling. | `Python` `BeautifulSoup` `SMTP` |
| [**Windows Admin Cheat Sheet**](https://github.com/CGFixIT/Windows-Admin-Cheat-Sheet) | Practical Windows administration references and repeatable operational commands. | `Windows` `PowerShell` `Sysadmin` |

---

## Engineering Approach

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

## Technology

<p align="center">
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white" alt="PowerShell" />
<img src="https://img.shields.io/badge/LangGraph-6C4AB6?style=flat-square" alt="LangGraph" />
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
<img src="https://img.shields.io/badge/ChromaDB-EA5A0C?style=flat-square" alt="ChromaDB" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" alt="SQLite" />
<img src="https://img.shields.io/badge/YARA-8B0000?style=flat-square" alt="YARA" />
<img src="https://img.shields.io/badge/Veeam-00B336?style=flat-square" alt="Veeam" />
<img src="https://img.shields.io/badge/Azure_AI-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Azure AI" />
<img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white" alt="Ollama" />
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

## Current Focus

- Expanding **CyClaw's governed agentic coding and local-model support**.
- Improving policy enforcement, evaluation, observability, and offline deployment paths.
- Turning hard-won infrastructure and recovery patterns into reusable security automation.

<div align="center">

**Atlanta, GA · Infrastructure · Data Protection · Security · Applied AI**

<sub>Building systems that remain useful after the demo ends.</sub>

</div>
