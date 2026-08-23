# Model Context Protocol (MCP) Portfolio

### Building Tool-Enabled AI Agents Through a Security and Governance Lens

![Microsoft Foundry](https://img.shields.io/badge/MICROSOFT%20FOUNDRY-Agent%20Platform-0078D4)
![Model Context Protocol](https://img.shields.io/badge/MODEL%20CONTEXT%20PROTOCOL-MCP-6F42C1)
![Focus](https://img.shields.io/badge/FOCUS-AI%20SECURITY-C62828)
![Methodology](https://img.shields.io/badge/METHODOLOGY-BUILD%20%7C%20VALIDATE%20%7C%20ANALYZE-2E7D32)

Hands-on exploration of **Model Context Protocol (MCP)** using Microsoft Foundry, Azure AI Services, Python, and Visual Studio Code.

The projects below examine MCP not only as an agent integration framework, but as an extension of the **AI security boundary** — introducing considerations around tool trust, authorization, identity, sensitive data, policy enforcement, and downstream guardrails.

---

## MCP Projects

### 🔌 Lab 1 — Microsoft Foundry MCP Tool Integration

**Remote MCP · FastMCP · Dynamic Tool Discovery · Multi-Tool Reasoning**

Integrated MCP capabilities with Microsoft Foundry using both a remote Microsoft Learn MCP server and a custom local FastMCP server.

* Validated remote and local MCP tool integration.
* Implemented dynamic tool discovery through a Python MCP client.
* Evaluated approval semantics, tool trust, and least-functionality.
* Performed negative testing that demonstrated successful tool execution does not guarantee correct agent policy decisions.

👉 **[View Lab 1 — MCP Tool Integration](README-ai-agents-mcp.md)**

---

### 🔗 Lab 2 — Text Analysis Agent with MCP

**Azure Language · PII Analysis · Entity Extraction · Sentiment Analysis**

Built a Microsoft Foundry text-analysis agent that accesses Azure Language capabilities through MCP.

* Validated PII detection and redaction through MCP.
* Tested named-entity, date, and sentiment analysis.
* Confirmed multi-tool orchestration from a single natural-language request.
* Examined MCP approval behavior, identity boundaries, sensitive-data handling, and tool exposure.

👉 **[View Lab 2 — Text Analysis Agent](README-text-agent-mcp.md)**

---

### 🎙️ Lab 3 — Azure Speech MCP Agent

**Azure Speech · Speech-to-Text · Text-to-Speech · Azure Blob Storage**

Integrated a Microsoft Foundry agent with the Azure Speech MCP Server and validated speech operations through both Foundry and a Python client.

* Validated speech-to-text and text-to-speech MCP workflows.
* Used Azure identity for client-to-Foundry authentication.
* Evaluated scoped Blob Storage access and protection of signed URLs.
* Observed downstream Foundry guardrail enforcement after successful MCP tool execution.

👉 **[View Lab 3 — Azure Speech MCP Agent](README-azure-speech-mcp-agent.md)**

---

## Security Perspective

Across all three projects, MCP consistently introduced a security boundary beyond the underlying language model.

Key observations included:

* **MCP servers and exposed tools become part of the trusted computing surface.**
* **Tool discovery should not imply automatic tool trust.**
* **Approval controls must represent meaningful authorization boundaries.**
* **Agent and tool identities should follow least-privilege principles.**
* **Sensitive data can cross multiple service and tool boundaries during agent execution.**
* **Successful tool execution does not guarantee correct, authorized, or policy-compliant agent behavior.**
* **Model guardrails and tool-level security controls operate at different layers and should be validated independently.**

The central security principle demonstrated throughout these projects is:

> **Giving an AI agent access to a tool expands what the agent can do — and expands what must be secured.**

---

## Technologies

**Microsoft Foundry** · **Model Context Protocol (MCP)** · **Azure AI Services** · **Azure Language** · **Azure Speech** · **Azure Blob Storage** · **FastMCP** · **Python** · **Azure Identity** · **Azure AI Projects SDK** · **OpenAI Responses API** · **Visual Studio Code**

---

[← Back to Knight AI Security Portfolio](../README.md)
