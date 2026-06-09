<!-- ========== HEADER ========== -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0,1a2a3a,01696f&height=160&section=header&text=Chris%20Grady&fontSize=48&fontColor=ffffff&fontAlignY=40&desc=Infrastructure%20Engineer%20%C2%B7%20AI%20Agent%20Builder%20%C2%B7%20Security%20Tooling&descAlignY=62&descSize=16" width="100%"/>

[![Website](https://img.shields.io/badge/cgfixit.com-01696f?style=for-the-badge&logo=safari&logoColor=white)](https://cgfixit.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/cgrady92)
[![Email](https://img.shields.io/badge/contact@cgfixit.com-333?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@cgfixit.com)
</div>

---

## 🗺️ Knowledge Map — My Domain Clusters

> My portfolio isn't a collection of random projects — it's a convergent architecture.
> The real differentiator lives **at the intersections**, not inside any single cluster.
>
> 🔗 **[View interactive force-graph map →](https://mail.cgfixit.com/Export/z/knowledge-map/)**

```
           🔒 Security / Detection
               YARA rules · PS1 scanner
               onion-link detection · OWASP
                        │
            ── BRIDGE ──┤── BRIDGE ──
        YARA pre-restore │  YARA → prompt injection
        malware-aware DR │  pattern defense for LLMs
                        │
  💾 Backup & DR ───────┼─────── 🤖 Local LLM / RAG
  Veeam VBR             │        LangGraph · ChromaDB
  proxy lifecycle       │        BM25+RRF · Ollama
  health-check ops      │        offline-first
                        │
            ── BRIDGE ──┤── BRIDGE ──
    VBR telemetry → AI  │  topology = policy enforcement
    remediation agents  │  soul governance · SQLite
                        │
              🛡️ AI Safety / Agent Governance
                  PsyClaw · soul drift detection
                  SHA-256 integrity · MCP server
                        │
              ⚙️ Automation / Sysadmin (substrate)
              PowerShell · SCCM · WinRM · VMware
```

---

## 🏗️ Projects by Cluster

### 🤖 AI Agents & Safety

| Repo | What it does | Stack |
|---|---|---|
| [**PsyClaw**](https://github.com/CGFixIT/PsyClaw) | Offline-first RAG agent — LangGraph topology as security policy, hybrid ChromaDB+BM25+RRF retrieval, SHA-256 soul drift detection, OWASP prompt sanitization, MCP server | `Python` `LangGraph` `ChromaDB` `FastAPI` `SQLite` |
| [**AzureAI-CopilotStudio-PersonalAgent-Instructions**](https://github.com/CGFixIT/AzureAI-CopilotStudio-PersonalAgent-Instructions) | Production-tested enterprise AI agent system instructions — tiered source hierarchy, anti-hallucination safeguards, VeeamGPT reference implementation | `Azure OpenAI` `Copilot Studio` `Prompt Engineering` |

### 🔒 Security / YARA Detection

| Repo | What it does | Stack |
|---|---|---|
| [**Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links**](https://github.com/CGFixIT/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links) | YARA ruleset + PowerShell scanner detecting Tor `.onion` C2s, BTC/XMR ransomware payment addresses in Veeam restore points — SIEM-ready JSON, Secure Restore integration | `PowerShell` `YARA` `Veeam` `Forensics` |

### 💾 Backup & DR Operations

| Repo | What it does | Stack |
|---|---|---|
| [**sccm-veeam-proxy-patching**](https://github.com/CGFixIT/sccm-veeam-proxy-patching) | Graceful Veeam proxy drain during SCCM patch windows — WinRM service management, Pre/Post task sequence, exit code 3010 support | `PowerShell` `SCCM` `VMware` `Veeam` |
| [**Veeam-HealthCheck-Simplifier**](https://github.com/CGFixIT/Veeam-HealthCheck-Simplifier) | CSV/JSON Veeam health check analyzer → PowerShell remediation output + Salesforce/Slack/Teams integration | `Python` `Veeam` `Analytics` |

### ⚙️ Automation / Scripting

| Repo | What it does | Stack |
|---|---|---|
| [**Scrape-n-Email**](https://github.com/CGFixIT/Scrape-n-Email) | Lightweight news/jobs scraper (RCP + Craigslist) with MIME-safe email delivery, formula-safe CSV, cross-platform logging | `Python` `BeautifulSoup` `SMTP` |

---

## 🧠 The Core Thesis

> *"Backups are operational memory and last-resort truth stores — backup infrastructure is a trustworthy-AI primitive."*

This means:
- **Veeam** is not just a backup tool — it's a **ground-truth substrate** for AI-assisted recovery decisions
- **YARA** is not just malware detection — it's the **prompt injection defense layer** for AI agents (see `sanitizer.py` in PsyClaw → next evolution: `yara-prompt-guard`)
- **PsyClaw** is not just orchestration — it's **security policy as code (LangGraph Topology** (`topology = enforcement`)

---

## 🛠️ Stack at a Glance

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white"/>
<img src="https://img.shields.io/badge/LangGraph-blueviolet?style=flat-square"/>
<img src="https://img.shields.io/badge/ChromaDB-orange?style=flat-square"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/YARA-darkred?style=flat-square"/>
<img src="https://img.shields.io/badge/Veeam-01a982?style=flat-square"/>
<img src="https://img.shields.io/badge/Azure_OpenAI-0089D6?style=flat-square&logo=microsoftazure&logoColor=white"/>
<img src="https://img.shields.io/badge/LM_Studio-607078?style=flat-square""/>
<img src="https://img.shields.io/badge/VMware-607078?style=flat-square&logo=vmware&logoColor=white"/>
<img src="https://img.shields.io/badge/SCCM-0078D7?style=flat-square&logo=windows&logoColor=white"/>
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white"/>
<img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white"/>
</p>

---

## 🔭 Currently Building

- **PsyClaw v1.3** — LangGraph topology rewrite, MCP server, OPA/Rego policy enforcement layer
- ???

---

<div align="center">
<sub>Atlanta, GA · Infrastructure Engineer → AI Agent Builder · Open to senior SRE / AI infrastructure / security engineering roles</sub>
</div>



<!--## Hi there 👋

<!--
**CGFixIT/CGFixIT** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
