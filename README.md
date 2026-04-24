# 🤖 Agentic AI Landscape

> **A comprehensive, framework-agnostic guide to Agentic AI — what it is, what's available, and how to choose.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Last Updated](https://img.shields.io/badge/Updated-2025-blue.svg)]()

---

## 📖 Table of Contents

- [What Is Agentic AI?](#what-is-agentic-ai)
- [How Agents Work](#how-agents-work)
- [The Agentic AI Landscape](#the-agentic-ai-landscape)
  - [Open-Source Frameworks](#open-source-frameworks)
  - [Cloud-Native Agent Platforms](#cloud-native-agent-platforms)
  - [Commercial Agent Orchestration](#commercial-agent-orchestration)
  - [Model Context Protocol (MCP) Ecosystems](#model-context-protocol-mcp-ecosystems)
  - [Evaluation & Observability](#evaluation--observability)
- [How to Choose the Right Framework](#how-to-choose-the-right-framework)
- [Decision Matrix](#decision-matrix)
- [Contributing](#contributing)

---

## What Is Agentic AI?

Traditional AI is **reactive** — you send a message, it replies. That's the end of the interaction.

**Agentic AI is proactive, autonomous, and action-oriented.** An AI agent:

1. **Receives a high-level goal** (e.g., "Research our top 5 competitors and write a market report")
2. **Plans a sequence of steps** to achieve that goal
3. **Uses tools** — web search, code execution, API calls, file I/O, database queries — to gather information and take action
4. **Adapts** when steps fail or new information changes the plan
5. **Delivers a result** without requiring step-by-step human instruction

This is a fundamental shift: from AI as a **tool you operate** to AI as an **agent you deploy**.

### Key Properties of an AI Agent

| Property | Description |
|----------|-------------|
| **Autonomy** | Acts without constant human input |
| **Goal-directedness** | Works toward a defined objective across multiple steps |
| **Tool use** | Accesses APIs, browsers, code interpreters, databases |
| **Memory** | Maintains context across steps (short-term) and sessions (long-term) |
| **Planning** | Breaks complex goals into executable sub-tasks |
| **Multi-agent coordination** | Can spawn or communicate with other agents |

### Real-World Examples

- A **coding agent** that reads a GitHub issue, writes the fix, runs tests, and opens a pull request
- A **research agent** that searches the web, synthesizes findings, and produces a structured report
- A **customer support agent** that looks up account data, troubleshoots issues, and escalates when needed
- A **security agent** that scans infrastructure, identifies misconfigurations, and files remediation tickets
- A **workflow automation agent** that monitors inboxes, classifies messages, and routes to the right system

---

## How Agents Work

```
┌─────────────────────────────────────────────────────────────────┐
│                        AGENTIC LOOP                             │
│                                                                 │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐  │
│  │  Receive │───▶│  Plan /  │───▶│ Execute  │───▶│ Evaluate │  │
│  │  Goal    │    │  Reason  │    │  Tools   │    │  Result  │  │
│  └──────────┘    └──────────┘    └──────────┘    └────┬─────┘  │
│                       ▲                               │        │
│                       └───────────────────────────────┘        │
│                         (loop until goal achieved)              │
└─────────────────────────────────────────────────────────────────┘
```

**Common agent patterns:**

- **ReAct** (Reason + Act) — Agent reasons about what to do, acts, observes the result, reasons again
- **Plan-and-Execute** — Agent creates a full plan first, then executes each step
- **Reflexion** — Agent critiques its own outputs and iterates
- **Multi-agent** — Multiple specialized agents collaborate, with an orchestrator coordinating
- **Tool-calling** — Agent selects from a defined set of tools (functions/APIs) to fulfill requests

---

## The Agentic AI Landscape

### Open-Source Frameworks

These frameworks give developers full control to build, customize, and self-host agentic systems.

| Framework | Description |
|-----------|-------------|
| **[LangChain](https://github.com/langchain-ai/langchain)** | The original LLM application framework; extensive tool integrations, chains, and agent abstractions |
| **[LangGraph](https://github.com/langchain-ai/langgraph)** | Graph-based agent orchestration from the LangChain team; excellent for stateful, multi-step, cyclical workflows |
| **[AutoGen](https://github.com/microsoft/autogen)** | Microsoft's multi-agent conversation framework; excels at agent-to-agent collaboration and debate |
| **[CrewAI](https://github.com/crewAIInc/crewAI)** | Role-based multi-agent framework where each agent has a defined persona, goal, and toolset |
| **[OpenAI Swarm](https://github.com/openai/swarm)** | OpenAI's lightweight, experimental multi-agent orchestration library; minimal and opinionated |
| **[Haystack](https://github.com/deepset-ai/haystack)** | Production-ready NLP pipeline framework with strong RAG and agent pipeline support |
| **[Semantic Kernel](https://github.com/microsoft/semantic-kernel)** | Microsoft's SDK for integrating LLMs into apps with native plugin/function-calling support (.NET, Python, Java) |
| **[Agno (formerly Phidata)](https://github.com/agno-agi/agno)** | Lightweight framework for building agents with memory, knowledge, and tools; fast and minimal |
| **[PydanticAI](https://github.com/pydantic/pydantic-ai)** | Type-safe agentic framework built on Pydantic; strong validation and structured outputs |
| **[Smolagents](https://github.com/huggingface/smolagents)** | Hugging Face's minimal agent library; focuses on code-as-actions, clean and hackable |
| **[Agency Swarm](https://github.com/VRSEN/agency-swarm)** | OpenAI Assistants API-based multi-agent framework with persistent threads and file handling |
| **[Camel-AI](https://github.com/camel-ai/camel)** | Research-oriented multi-agent framework for role-playing simulations and cooperative agents |
| **[Atomic Agents](https://github.com/BrainBlend-AI/atomic-agents)** | Composable, modular agent framework built around atomic (single-responsibility) agent components |

---

### Cloud-Native Agent Platforms

Fully managed services from major cloud providers — best for enterprises that want to build without managing infrastructure.

| Platform | Provider | Description |
|----------|----------|-------------|
| **[OpenAI Agents SDK](https://openai.github.io/openai-agents-python/)** | OpenAI | Official Python SDK for building agents with built-in tool use, handoffs, and guardrails on GPT-4o |
| **[Google Agent Development Kit (ADK)](https://google.github.io/adk-docs/)** | Google | Production framework for building multi-agent systems on Gemini; designed for enterprise deployment |
| **[Google Vertex AI Agent Builder](https://cloud.google.com/products/agent-builder)** | Google Cloud | No-code/low-code tool for building agents with Gemini on Vertex AI |
| **[Amazon Bedrock Agents](https://aws.amazon.com/bedrock/agents/)** | AWS | Fully managed agentic service on Bedrock; integrates with Lambda, S3, and AWS knowledge bases |
| **[Azure AI Agent Service](https://azure.microsoft.com/en-us/products/ai-services/ai-agent-service)** | Microsoft Azure | Managed agent runtime on Azure; integrates with OpenAI models, Azure Functions, and enterprise data |
| **[IBM watsonx Orchestrate](https://www.ibm.com/products/watsonx-orchestrate)** | IBM | Enterprise AI automation platform with skill-based agent orchestration |
| **[Salesforce Agentforce](https://www.salesforce.com/agentforce/)** | Salesforce | CRM-native AI agent platform for customer service, sales, and marketing automation |

---

### Commercial Agent Orchestration

Dedicated commercial platforms built specifically for enterprise agentic workflows.

| Platform | Description |
|----------|-------------|
| **[Langfuse](https://langfuse.com)** | Open-source LLM engineering platform with agent tracing, prompt management, and evaluation |
| **[LlamaIndex](https://www.llamaindex.ai/)** | Data framework for LLM applications with strong agent + RAG integration |
| **[Dust](https://dust.tt)** | Enterprise multi-agent workspace connecting to company data and tools |
| **[Voiceflow](https://www.voiceflow.com/)** | Visual agent design platform for conversational AI; strong for customer-facing deployments |
| **[Botpress](https://botpress.com/)** | Open-source conversational AI platform with agentic workflow capabilities |
| **[Fixie.ai](https://fixie.ai)** | Platform for building and deploying conversational agents with tool integrations |

---

### Model Context Protocol (MCP) Ecosystems

[MCP](https://modelcontextprotocol.io) is an open standard (developed by Anthropic) that defines how AI agents connect to external tools, data sources, and services. Think of it as USB-C for AI integrations.

| Resource | Description |
|----------|-------------|
| **[MCP Specification](https://modelcontextprotocol.io/specification)** | The official protocol spec — how servers expose tools, resources, and prompts to agents |
| **[Anthropic MCP SDK](https://github.com/modelcontextprotocol/python-sdk)** | Official Python SDK for building MCP servers and clients |
| **[MCP Server Registry](https://github.com/modelcontextprotocol/servers)** | Official curated list of MCP servers (GitHub, Slack, Postgres, filesystem, etc.) |
| **[Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers)** | Community-maintained list of 500+ MCP servers across every category |
| **[Claude Desktop + MCP](https://claude.ai/download)** | Claude's desktop app supports MCP natively; connects agents to local and remote MCP servers |

---

### Evaluation & Observability

You can't improve what you can't measure. These tools help you understand what your agents are actually doing.

| Tool | Description |
|------|-------------|
| **[LangSmith](https://smith.langchain.com/)** | LangChain's tracing, evaluation, and monitoring platform for agents and chains |
| **[Langfuse](https://langfuse.com)** | Open-source observability platform with session tracing, cost tracking, and evals |
| **[AgentOps.ai](https://agentops.ai)** | Purpose-built observability platform for AI agents; session replays, cost analytics |
| **[Helicone](https://helicone.ai)** | LLM observability proxy; logs every request/response across any provider |
| **[Braintrust](https://braintrust.dev)** | LLM evaluation and dataset management platform |
| **[RAGAS](https://github.com/explodinggradients/ragas)** | Evaluation framework specifically for RAG pipelines and retrieval quality |
| **[Phoenix (Arize)](https://phoenix.arize.com/)** | Open-source LLM tracing and evaluation with OTEL support |

---

## How to Choose the Right Framework

Use these questions to narrow your selection:

### 1. What is your deployment context?

| Context | Recommended Starting Point |
|---------|---------------------------|
| Cloud-first enterprise | Amazon Bedrock Agents, Azure AI Agent Service, or Google ADK |
| Full control / self-hosted | LangGraph, AutoGen, or CrewAI |
| Lightweight prototyping | Smolagents, PydanticAI, or OpenAI Agents SDK |
| Multi-agent research | AutoGen, Camel-AI |
| Production RAG + agents | LlamaIndex, Haystack |

### 2. How complex is your agent workflow?

| Workflow Type | Best Framework |
|---------------|---------------|
| Linear, single-agent task | OpenAI Agents SDK, Smolagents |
| Cyclical / stateful loops | LangGraph |
| Multi-agent collaboration | AutoGen, CrewAI |
| Role-based teams of agents | CrewAI, Agency Swarm |
| Code execution-heavy | AutoGen (with Docker executor), Smolagents |

### 3. What's your language / stack?

| Stack | Options |
|-------|---------|
| Python | All frameworks above |
| TypeScript / JavaScript | LangChain.js, Mastra |
| .NET / C# | Semantic Kernel |
| Java | Semantic Kernel, Spring AI |
| Low/no-code | Google Vertex Agent Builder, Voiceflow, Botpress |

### 4. How important is production observability?

If you're going to production, pair any framework with **LangSmith**, **Langfuse**, or **AgentOps.ai** from day one. Retrofitting observability is painful.

---

## Decision Matrix

```
                        CONTROL vs. SPEED TO PRODUCTION
                        
  Full Control ◄────────────────────────────────► Managed Service
       │                                                    │
  LangGraph                                    Amazon Bedrock Agents
  AutoGen                                      Azure AI Agent Service
  CrewAI          PydanticAI    OpenAI          Google ADK
  Smolagents      LlamaIndex    Agents SDK      Salesforce Agentforce
       │                                                    │
  Complex Multi-Agent ◄───────────────────► Single-Agent Tasks
```

---

## ⚠️ A Note on Security

Choosing a framework is only the beginning. How you configure your agents matters more than which framework you use.

**Before you ship any agent to production, ask yourself:**
- Have I applied least-privilege to every API key this agent uses?
- Does this agent have access to only the data it needs for its specific task?
- Is every agent action logged and auditable?
- Have I validated agent outputs before they reach downstream systems?
- Are my MCP server connections authenticated and scoped?

For a security-first operational guide, see → [agentops-security-workflows](https://github.com/YOUR_USERNAME/agentops-security-workflows)

For Cisco's open-source AI security tools → [cisco-ai-security-toolkit](https://github.com/YOUR_USERNAME/cisco-ai-security-toolkit)

---

## Contributing

This repo is intended as a living document. If you know of a framework that belongs here, or if any links are outdated, please open a PR.

1. Fork this repo
2. Add your framework/tool to the appropriate section with a one-line description and link
3. Open a pull request

---

*Maintained with ❤️ for the AI builder community.*
