<h1 align="center">Chris Grady</h1>

<p align="center">
  <strong>Systems &amp; Solutions Engineer</strong><br />
  Atlanta, GA · Infrastructure · Security · Applied AI
</p>

<p align="center">
  <a href="https://cgfixit.com">Website</a> ·
  <a href="https://linkedin.com/in/cgrady92">LinkedIn</a> ·
  <a href="mailto:contact@cgfixit.com">Email me</a>
</p>

I build automation that helps operators protect data, understand their systems, and use AI with explicit controls. My work connects infrastructure and recovery experience with practical **Python, PowerShell, and Rust** engineering.

[Featured projects](#featured-projects) · [More projects](#more-projects) · [How I build](#how-i-build) · [Get in touch](#get-in-touch)

## Featured projects

### [CyClaw Net Viewer](https://github.com/cgfixit/Mac-NetViewer-EZview) · macOS network visibility

<sub>Latest project · Created September 6, 2026 · Repository: Mac-NetViewer-EZview</sub>

A TCPView-inspired desktop app and CLI for seeing which processes own TCP/UDP connections on a Mac. Built to inspect network activity while working on CyClaw's telemetry controls.

- **Inspect connections:** process names, PIDs, IPv4/IPv6 endpoints, connection states, and an off-box filter.
- **Follow changes:** color-coded connection events, background DNS resolution, and CSV exports.
- **Use either interface:** an egui desktop app and a scriptable CLI, with macOS packaging for Apple Silicon and Intel.

**Stack:** Rust · egui/eframe · macOS socket APIs<br />
[Build and run](https://github.com/cgfixit/Mac-NetViewer-EZview/blob/master/docs/BUILD.md) · [Design](https://github.com/cgfixit/Mac-NetViewer-EZview/blob/master/docs/DESIGN.md) · [Tests](https://github.com/cgfixit/Mac-NetViewer-EZview/tree/master/tests)

### [CyClaw](https://github.com/cgfixit/CyClaw) · local AI with explicit controls

An offline-first AI backend for querying a local knowledge base, with retrieval before generation and a governed coding workflow for real repositories.

- **Control the request path:** hybrid search combines semantic and keyword retrieval; LangGraph routes requests through explicit confirmation and audit steps.
- **Keep changes reviewable:** the optional coding harness separates patching, verification, human approval, pushing, and draft-PR creation.
- **Make state inspectable:** audit logs and integrity checks, plus optional user accounts and a memory store with proposal/apply controls. The coding layer, accounts, and memory ship disabled.

**Stack:** Python · FastAPI · LangGraph · ChromaDB · BM25/RRF · Ollama · SQLite · MCP<br />
[Architecture](https://github.com/cgfixit/CyClaw#architecture) · [Setup guide](https://github.com/cgfixit/CyClaw/blob/main/setup-guide.md) · [Tests](https://github.com/cgfixit/CyClaw/tree/main/tests)

[Explore the CyClawOS UI demo](https://o3mjwe6dliqf6.kimi.page/) · [Alternate demo](https://cyclaw-demo-cgrady92.grok.me)<br />
<sub>CyClawOS is a browser simulation of the interface and workflows; the Python backend is a separate project linked above.</sub>

### [Veeam YARA Scanner](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links) · recovery inspection

PowerShell and YARA tooling for inspecting mounted recovery data for ransomware-related indicators before it returns to service.

- **Look for suspicious infrastructure:** Tor, I2P, and Freenet indicators with context-aware rules.
- **Support investigation:** structured JSON findings, matched strings, and scan logs for recovery and security workflows.
- **Exercise failure paths:** Pester tests cover scanner logic and mocked Veeam integration; YARA fixtures cover detections and false-positive exclusions.

**Stack:** PowerShell · YARA · Veeam · Pester<br />
[Scanner source](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links/blob/main/Veeam-YARA-SecureRestore.ps1) · [Rules](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links/blob/main/yara-malware-detection.yara) · [Test guide](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links/blob/main/tests/README.md)

### [Veeam Proxy Maintenance](https://github.com/cgfixit/sccm-veeam-proxy-patching) · coordinated patch windows

Coordinates VMware backup proxies around SCCM/ConfigMgr maintenance from a VBR server or management host.

- **Drain before stopping:** disable selected proxies, wait for their active tasks, then stop services.
- **Restore availability:** restart services and re-enable proxies in a separate post-maintenance stage.
- **Give operators a result:** configurable timeouts, logs, preview support, and SCCM-aware exit codes.

**Stack:** PowerShell · Veeam · SCCM/ConfigMgr · WinRM · VMware<br />
[Implementation](https://github.com/cgfixit/sccm-veeam-proxy-patching/blob/main/sccmpatch.ps1) · [Tests](https://github.com/cgfixit/sccm-veeam-proxy-patching/tree/main/tests)

## More projects

| Project | What it demonstrates |
| :--- | :--- |
| [**Veeam HealthCheck Simplifier**](https://github.com/cgfixit/Veeam-HealthCheck-Simplifier) | Python analysis of CSV/JSON health exports into reports, PowerShell remediation previews, and ticket payloads. Optional Salesforce/Slack delivery. |
| [**Insight Extractor**](https://github.com/cgfixit/Insight_Extractor) | Python NLP pipeline combining regex, dynamic keywords, and transformer-based semantic scoring to turn long text into structured security insights. |
| [**AI Agent Instruction Templates**](https://github.com/cgfixit/AzureAI-CopilotStudio-PersonalAgent-Instructions) | Reusable templates and domain examples for source grounding, version checks, tool scope, and escalation, including newer model-specific variants. |
| [**Systems Administration Handbook**](https://github.com/cgfixit/Windows-Linux--Docker-Handbook) | Windows, Linux, and macOS references updated for 2026, plus an initial Docker reference. [Browse the Windows web app](https://cgfixit.github.io/Windows-Linux--Docker-Handbook/). |
| [**Polymarket Mimic Trader**](https://github.com/cgfixit/PolyMarket_Mimic_Trader) | Async Python research bot with trader scoring, exposure limits, circuit breakers, and SQLite tracking. **Paper mode only; live execution is disabled.** |
| [**Scrape-n-Email**](https://github.com/cgfixit/Scrape-n-Email) | Python scraping and email digests with retry handling, CSV formula escaping, typed configuration, and offline pipeline tests. |

## How I build

- **Start with an operational constraint.** A backup task must finish before maintenance; a local AI request needs explicit permission before using a cloud provider.
- **Put controls in the implementation.** Use scoped access, validation, confirmation gates, and inspectable logs.
- **Test the failure paths.** Cover timeouts, malformed input, unavailable dependencies, and denied actions alongside normal operation.
- **Make the next step clear.** Provide usable interfaces, setup instructions, examples, and reviewable output.

<details>
<summary><strong>Technology across the portfolio</strong></summary>

- **Languages:** Python, PowerShell, Rust, Bash.
- **Infrastructure:** Veeam, VMware, SCCM/ConfigMgr, WinRM, Windows, Linux, macOS, Docker.
- **AI and data:** FastAPI, LangGraph, Ollama, ChromaDB, BM25/RRF, Sentence-Transformers, Pydantic, SQLite, MCP.
- **Validation and security:** pytest, Pester, Rust tests and Clippy, GitHub Actions, YARA.

</details>

## Get in touch

I'm interested in systems and solutions engineering, infrastructure automation, security tooling, and applied AI work. If your team needs someone who can connect operational requirements to working software, let's talk.

[**Email: contact@cgfixit.com**](mailto:contact@cgfixit.com) · [LinkedIn](https://linkedin.com/in/cgrady92) · [Website](https://cgfixit.com)

<sub>Project information reviewed September 6, 2026. This selection covers my public, non-archived original projects; archived work and third-party forks are outside this portfolio.</sub>
