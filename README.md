# B&R Code Assistant (`br-code-assistant`)

[![Status](https://img.shields.io/badge/Status-Superseded_by_MCP_Suite-blue)](https://github.com/controlguy-ys/br-automation-pvi-mcp-server)
[![Domain](https://img.shields.io/badge/Domain-B%26R_Automation_Studio-FF6600)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#)

Initial prototype workspace for AI-assisted **B&R Automation Studio** code generation, project structure analysis, and compiler error triage.

> [!IMPORTANT]
> **Active Development Has Moved to the Modular MCP Ecosystem:**
> This initial monolithic assistant concept has been superseded by modular, standards-based **Model Context Protocol (MCP)** servers and reference architectures that work seamlessly across **OpenAI Codex**, **Claude Code**, and MCP-compatible IDE harnesses:
>
> 1. **[`br-automation-pvi-mcp-server`](https://github.com/controlguy-ys/br-automation-pvi-mcp-server)** — **Full 38-tool MCP Server & C# PVI Companion** for B&R Automation Studio (`BR.AS.Build.exe` CLI compilation, ANSL/TCP PLC & ArSim connectivity, SQLite variable indexing, `10–100ms` real-time trending, and `confirm: true` safety-gated controller operations).
> 2. **[`BnRClaudePlugin`](https://github.com/controlguy-ys/BnRClaudePlugin)** — **Lightweight 5-tool Plugin (`br-build`)** for recursive `.apj` project scanning, hardware configuration inspection, CLI builds, and structured compiler diagnostic parsing.
> 3. **[`automation-engineering-with-codex`](https://github.com/controlguy-ys/automation-engineering-with-codex)** — **Reference Architecture & Playbook** for applying OpenAI Codex and Verifiable Agent Harnesses (`Task – Proof – Check`) to industrial automation engineering.

---

## Architectural Evolution: From Prompt Wrapper to Verifiable MCP Harness

Early experiments with LLM-based PLC code assistants showed that prompt engineering alone cannot prevent hallucinated hardware configurations or unverified runtime behavior in B&R Automation Studio (`.apj`, `.pkg`, `.var`, `.typ`).

By decomposing `br-code-assistant` into deterministic MCP tool servers:
- **Compiler Grounding**: Agents invoke `build_project` and `parse_build_log` via [`BnRClaudePlugin`](https://github.com/controlguy-ys/BnRClaudePlugin) to verify every generated Structured Text (IEC 61131-3) or ANSI C/C++ change against `BR.AS.Build.exe`.
- **Live Runtime Verification**: Agents query indexed PLC symbols in SQLite and capture `10–100ms` real-time trend traces via [`br-automation-pvi-mcp-server`](https://github.com/controlguy-ys/br-automation-pvi-mcp-server) to prove control-loop stability on ArSim or physical PLC targets.
- **Safety Gating**: Destructive target operations (`Coldstart`, `Warmstart`, `Diagnostics`) are protected by a deterministic Guard Layer requiring explicit user confirmation.

## Quick Links

- **Full PVI & Build MCP Server (38 Tools)**: [`https://github.com/controlguy-ys/br-automation-pvi-mcp-server`](https://github.com/controlguy-ys/br-automation-pvi-mcp-server)
- **Build-Only Plugin (5 Tools)**: [`https://github.com/controlguy-ys/BnRClaudePlugin`](https://github.com/controlguy-ys/BnRClaudePlugin)
- **Codex Industrial Harness Architecture**: [`https://github.com/controlguy-ys/automation-engineering-with-codex`](https://github.com/controlguy-ys/automation-engineering-with-codex)
- **Controls Engineering Knowledge Graph**: [`https://github.com/controlguy-ys/AutomataWiki`](https://github.com/controlguy-ys/AutomataWiki)
