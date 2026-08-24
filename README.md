<div align="center">
  <h1>✨ Awesome A2A (Agent2Agent Protocol) ✨</h1>

  <img src="assets/banner.png" alt="Awesome A2A Banner - Abstract network or connection graphic" width="100%">

  <p align="center">
    A curated list of awesome resources, implementations, tools, and examples related to the <strong>Agent2Agent (A2A) Protocol</strong> for AI agent interoperability.
  </p>

  <!-- Keep these links. Translations will automatically update with the README. -->
  <p align="center">
    <a href="https://zdoc.app/de/ai-boost/awesome-a2a">Deutsch</a> |
    <a href="https://zdoc.app/en/ai-boost/awesome-a2a">English</a> |
    <a href="https://zdoc.app/es/ai-boost/awesome-a2a">Español</a> |
    <a href="https://zdoc.app/fr/ai-boost/awesome-a2a">français</a> |
    <a href="https://zdoc.app/ja/ai-boost/awesome-a2a">日本語</a> |
    <a href="https://zdoc.app/ko/ai-boost/awesome-a2a">한국어</a> |
    <a href="https://zdoc.app/pt/ai-boost/awesome-a2a">Português</a> |
    <a href="https://zdoc.app/ru/ai-boost/awesome-a2a">Русский</a> |
    <a href="https://zdoc.app/zh/ai-boost/awesome-a2a">中文</a>
  </p>

  <p align="center">
    <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a>
    <a href="https://opensource.org/license/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
    <a href="https://github.com/ai-boost/awesome-a2a"><img src="https://img.shields.io/github/stars/ai-boost/awesome-a2a.svg?style=social&label=Star" alt="GitHub stars"></a>
    <a href="https://github.com/ai-boost/awesome-a2a"><img src="https://img.shields.io/github/forks/ai-boost/awesome-a2a.svg?style=social&label=Fork" alt="GitHub forks"></a>
  </p>
</div>

> The Agent2Agent (A2A) Protocol is revolutionizing how AI agents communicate and collaborate - enabling seamless interoperability across different frameworks, vendors, and platforms. This repository collects the best resources to help developers build A2A-compatible agents.


## Contents

*   [🤔 What is A2A? (Briefly)](#-what-is-a2a-briefly)
*   [💡 Key Principles](#-key-principles)
*   [⚙️ How Does A2A Work? (High Level)](#️-how-does-a2a-work-high-level)
*   [🚀 Getting Started with A2A](#-getting-started-with-a2a)
*   [🏛️ Official Resources](#️-official-resources)
*   [📜 Specification & Core Concepts](#-specification--core-concepts)
*   [⚙️ Implementations & Libraries](#️-implementations--libraries)
    *   [Official Samples](#official-samples)
    *   [Framework Integrations (Official Samples)](#framework-integrations-official-samples)
    *   [Community Implementations](#community-implementations)
        *   [SDKs & Libraries (by language)](#sdks--libraries-by-language)
        *   [Frameworks](#frameworks)
        *   [Platforms & Integrated Solutions](#platforms--integrated-solutions)
*   [🛠️ Tools & Utilities](#️-tools--utilities)
*   [📚 Tutorials & Articles](#-tutorials--articles)
*   [🎬 Demos & Examples](#-demos--examples)
*   [🔗 Related Protocols & Concepts](#-related-protocols--concepts)
*   [💬 Community](#-community)
*   [Contributing](#contributing)

---

## 🤔 What is A2A? (Briefly)

A2A (Agent2Agent) is an **open protocol** from Google and partners enabling different **AI agents** (from various vendors/frameworks) to **communicate securely** and **collaborate on tasks**. It aims to break down silos between isolated agent systems, allowing for more complex cross-application automation.

**⭐ Official Website:** [a2aproject.github.io/A2A](https://a2aproject.github.io/A2A) | **⭐ Official GitHub:** [github.com/a2aproject/A2A](https://github.com/a2aproject/A2A) | 🌐 **Multilingual Docs (EN/ZH/JA):** [agent2agent.ren](https://agent2agent.ren)

## 💡 Key Principles

*   **Simple:** Uses existing standards (HTTP, JSON-RPC, SSE).
*   **Enterprise Ready:** Focuses on Auth, Security, Privacy, Monitoring.
*   **Async First:** Handles long-running tasks & human-in-the-loop.
*   **Modality Agnostic:** Supports Text, Files, Forms, Streams, etc.
*   **Opaque Execution:** Agents interact without sharing internal logic/tools.

## ⚙️ How Does A2A Work? (High Level)

1.  **Discovery:** Agents publish an `Agent Card` (JSON) describing capabilities, endpoint, and auth needs.
2.  **Communication:** A `Client` agent sends a `Task` request (containing a `Message` with `Parts`) to a `Remote Agent (Server)` using HTTP/JSON-RPC 2.0.
3.  **Execution & Response:** The Server processes the task, updating its `status`. It responds with the final status and any generated `Artifacts` (results, also containing `Parts`).
4.  **Updates:** For long tasks, the Server can optionally stream `TaskStatusUpdateEvent` or `TaskArtifactUpdateEvent` via Server-Sent Events (SSE) or use Push Notifications.

*For details, see the [Official Technical Documentation](https://a2aproject.github.io/A2A/#/documentation).*

---

## 🚀 Getting Started with A2A

New to A2A? Here's a suggested path:

1.  **Understand the Basics:** Read the sections above ([What is A2A?](#-what-is-a2a-briefly), [Key Principles](#-key-principles), [How it Works](#️-how-does-a2a-work-high-level)). Check the 📰 [Announcement Blog Post](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/).
2.  **Explore Core Concepts:** Dive into the 📖 [Official Technical Documentation](https://a2aproject.github.io/A2A/#/documentation), focusing on `Agent Card`, `Task`, `Message`, `Part`, and `Artifact`.
3.  **See it in Action:** Watch the 🎥 [Official Demo Video](https://storage.googleapis.com/gweb-developer-goog-blog-assets/original_videos/A2A_demo_v4.mp4) and explore the code for the 🌐 [Multi-Agent Web App Demo](https://github.com/a2aproject/A2A/tree/v0.2.1/demo).
4.  **Run the Samples:** Clone the [Official Samples Repo](https://github.com/a2aproject/a2a-samples) and follow its instructions to run a client (like the CLI) and a sample agent (e.g., LangGraph or Genkit agent).
5.  **Review the Code:** Look at the `common` (Python) or `server`/`client` (JS/TS) libraries in the official samples to see how A2A communication is implemented.
6.  **Try Building:** Adapt a sample or use a library to create your own basic A2A agent or client.

---

## 🏛️ Official Resources

*   📄 [A2A Protocol Website](https://a2aproject.github.io/A2A) - The main documentation site.
*   💻 [google/A2A GitHub Repository](https://github.com/a2aproject/A2A) - Source code for the spec, docs, and official samples.
*   📰 [Google Developers Blog Post](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/) - Announcement blog post explaining the motivation and partners.
*   📰 [Announcing ADK for Java 1.0.0: Building the Future of AI Agents in Java](https://developers.googleblog.com/en/announcing-adk-for-java-100-building-the-future-of-ai-agents-in-java/) - Official March 2026 launch of the Agent Development Kit (ADK) for Java 1.0.0, introducing native A2A protocol support, Google Maps grounding, human-in-the-loop workflows, and robust session management for building scalable Java agents.
*   📰 [How A2A is Building a World of Collaborative Agents](https://developers.googleblog.com/how-a2a-is-building-a-world-of-collaborative-agents/) - 2026 official update on real-world A2A adoption, partner momentum, and the growing agent ecosystem.
*   🏷️ [A2A Protocol v1.0.0 Release](https://github.com/a2aproject/A2A/releases/tag/v1.0.0) - Official March 2026 v1.0.0 release marking the first stable A2A specification milestone, including release notes, breaking changes, and conformance updates.
*   🏷️ [A2A Protocol v1.0.1 Release](https://github.com/a2aproject/A2A/releases/tag/v1.0.1) - Official May 2026 v1.0.1 patch release with HTTP binding, transcoding error, and TaskStatus specification fixes following the v1.0.0 milestone.

## 📜 Specification & Core Concepts

*(See [How Does A2A Work?](#️-how-does-a2a-work-high-level) above for summaries)*

*   📖 [A2A Technical Documentation](https://a2aproject.github.io/A2A/#/documentation) - **(Full Details)** Detailed explanation of actors, transport, auth, core objects (Task, Artifact, Message, Part), Agent Card, etc.
*   📄 [JSON Specification](https://github.com/a2aproject/A2A/tree/main/specification/json) - The raw JSON schema definition for A2A structures.
*   💡 [Key Principles (Docs)](https://a2aproject.github.io/A2A/#/documentation?id=key-principles) - Link to the principles section in the official docs.
*   🃏 [Agent Card Specification (Docs)](https://a2aproject.github.io/A2A/#/documentation?id=agent-card) - Link to the Agent Card section in the official docs.
*   🗺️ [Agent Discovery (Topic)](https://a2aproject.github.io/A2A/#/topics/agent_discovery.md) - Discussion on how clients can find agent cards.
*   🔔 [Push Notifications (Topic)](https://a2aproject.github.io/A2A/#/topics/push_notifications.md) - Details on the push notification mechanism.
*   🛡️ [Enterprise Readiness (Topic)](https://a2aproject.github.io/A2A/#/topics/enterprise_ready.md) - Discussion on security, auth, privacy aspects.
*   🔐 [OID4VP In-Task Authorization Extension](https://github.com/a2aproject/experimental-ext-oid4vp-auth) - **Official** experimental extension for using OpenID for Verifiable Presentations (OID4VP) to perform Just-In-Time (JIT) in-task authorization, allowing server agents to request verifiable presentations from clients during task execution. Includes a sample implementation and an [A2A + OID4VP integration demo](https://github.com/hiero-ledger/heka-identity-platform/tree/main/demo/a2a-oid4vp).
*   🔌 [SLIMRPC Custom Protocol Binding](https://github.com/a2aproject/experimental-cpb-slimrpc) - **Official** experimental custom protocol binding for A2A over SLIM (Secure Low-Latency Interactive Messaging), providing a secure, low-latency transport option for agent-to-agent communication.

## ⚙️ Implementations & Libraries

#### Official Samples

*These demonstrate basic A2A client/server communication.*

| Language          | Sample Name                | One-line Description                                         | GitHub URL                                                                                                                                                                              |
| ----------------- | -------------------------- | ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🔷 **TypeScript** | Genkit SDK Core            | TS SDK + CLI, builds shared code for front- and backend      | [https://github.com/a2aproject/a2a-samples/tree/main/samples/js](https://github.com/a2aproject/a2a-samples/tree/main/samples/js)                                                        |
|                   | Movie Recommendation Agent | Movie-recommendation conversational agent built with Genkit  | [https://github.com/a2aproject/a2a-samples/tree/main/samples/js/src/agents/movie-agent](https://github.com/a2aproject/a2a-samples/tree/main/samples/js/src/agents/movie-agent)                                |
|                   | TypeScript Client          | Pure-frontend call example written in TS                     | [https://github.com/a2aproject/a2a-samples/tree/main/samples/js/client](https://github.com/a2aproject/a2a-samples/tree/main/samples/js/client)                                          |
|                   | Node Express Server        | A2A HTTP service implemented with Node/Express               | [https://github.com/a2aproject/a2a-samples/tree/main/samples/js/server](https://github.com/a2aproject/a2a-samples/tree/main/samples/js/server)                                          |
| ☕ **Java**        | Custom Client              | Java client with streaming listener                          | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/custom_java_impl/client](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/custom_java_impl/client)    |
|                   | Data Models                | Complete set of POJO data models                             | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/custom_java_impl/model](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/custom_java_impl/model)      |
|                   | Custom Server              | Spring Boot A2A server implementation                        | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/custom_java_impl/server](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/custom_java_impl/server)    |
|                   | Dice Agent (Multi-Transport) | Agent supporting multiple transport protocols              | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/dice_agent_multi_transport](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/dice_agent_multi_transport) |
|                   | Magic 8-Ball (Security)    | Security-focused agent with OAuth2                           | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/magic_8_ball_security](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/magic_8_ball_security) |
|                   | Content Writer Agent       | Content generation agent                                     | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/content_writer](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/content_writer)        |
|                   | Content Editor Agent       | Content editing agent                                        | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/content_editor](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/content_editor)        |
|                   | Weather MCP Agent          | Weather agent with MCP integration                           | [https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/weather_mcp](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/weather_mcp)              |
| 💠 **.NET**       | Basic A2A Demo             | Echo and Calculator server examples                          | [https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/BasicA2ADemo](https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/BasicA2ADemo)                      |
|                   | CLI Demo                   | Command-line client and server demo                          | [https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/A2ACliDemo](https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/A2ACliDemo)                          |
|                   | Semantic Kernel Demo       | Integration with Semantic Kernel                             | [https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/A2ASemanticKernelDemo](https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/A2ASemanticKernelDemo)    |
| 🐍 **Python**     | CLI Host                   | Command-line interface for interacting with A2A agents       | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/hosts/cli](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/hosts/cli)                                        |
|                   | Hello World                | Recommended first-run "Hello World" scaffold                 | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/helloworld](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/helloworld)                          |
|                   | LangGraph Agent            | Uses LangGraph to orchestrate multi-turn dialogue            | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/langgraph](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/langgraph)                            |
|                   | CrewAI Agent               | Demonstrates multi-role collaboration with CrewAI            | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/crewai](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/crewai)                                  |
|                   | Semantic Kernel Agent      | Orchestrates tools with Semantic Kernel                      | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/semantickernel](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/semantickernel)                  |
|                   | AG2 Agent                  | Minimal AG2 mutual-call example                              | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/ag2](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/ag2)                                        |
|                   | ADK Expense Reimbursement  | Multi-turn expense reimbursement with forms                  | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/adk_expense_reimbursement](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/adk_expense_reimbursement) |
|                   | Birthday Planner (ADK)     | Multi-step birthday-party planner with ADK                   | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/birthday_planner_adk](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/birthday_planner_adk)    |
|                   | Azure AI Foundry Agent     | Example using Azure AI Foundry SDK                           | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/azureaifoundry_sdk](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/azureaifoundry_sdk)         |
|                   | A2A MCP Integration        | Multi-agent collaboration with MCP servers                   | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/a2a_mcp](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/a2a_mcp)                              |
|                   | MCP without Framework      | Bare-metal MCP integration without frameworks                | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/a2a-mcp-without-framework](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/a2a-mcp-without-framework) |
|                   | Travel Planner Agent       | One-stop travel-planning agent                               | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/travel_planner_agent](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/travel_planner_agent)    |
|                   | Headless OAuth2            | OAuth2 flow for headless agents                              | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/headless_agent_auth](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/headless_agent_auth)      |
|                   | Analytics Workflow         | Multi-agent orchestration for data-analytics                 | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/analytics](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/analytics)                            |
|                   | A2A Telemetry              | Collects and displays agent telemetry data                   | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/a2a_telemetry](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/a2a_telemetry)                   |
|                   | Multiagent Host            | Comprehensive multi-agent orchestration example              | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/hosts/a2a_multiagent_host](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/hosts/a2a_multiagent_host)        |
|                   | GitHub Agent               | Agent with GitHub toolset integration                        | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/github-agent](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/github-agent)                      |
|                   | Veo Video Generator        | Generates video via Veo API                                  | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/veo_video_gen](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/veo_video_gen)                  |
|                   | LlamaIndex File Chat       | Q&A retrieval over local files                               | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/llama_index_file_chat](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/llama_index_file_chat) |
|                   | Marvin Agent               | Builds domain agents with Marvin                             | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/marvin](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/marvin)                                  |
|                   | MindsDB Agent              | Calls MindsDB for prediction and querying                    | [https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/mindsdb](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/mindsdb)                                |
| 🐹 **Go**         | Go Reference Impl          | Full A2A server + client implemented in Go                   | [https://github.com/a2aproject/a2a-samples/tree/main/samples/go](https://github.com/a2aproject/a2a-samples/tree/main/samples/go)                                                        |

> **Quick Start**
> First-time users: try **TypeScript `Movie Recommendation Agent`**, **Python `Hello World`**, or **Go `Go Reference Impl`** — minimal dependencies and the simplest startup commands.

#### Framework Integrations (Official Samples)

*These show how agents built with specific frameworks can expose an A2A interface.*

| Language   | Agent Framework | Agent Description                           | Key A2A Features Demonstrated         | Link                                                                           |
| :--------- | :-------------- | :------------------------------------------ | :-------------------------------------- | :----------------------------------------------------------------------------- |
| 🐍 Python  | LangGraph       | Multi-turn dialogue orchestration           | Tools, Streaming, Multi-turn          | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/langgraph) |
| 🐍 Python  | CrewAI          | Multi-role collaboration                    | Non-textual Artifacts (Files)         | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/crewai)   |
| 🐍 Python  | Google ADK      | Expense reimbursement                       | Multi-turn, Forms (DataPart)          | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/adk_expense_reimbursement)|
| 🐍 Python  | Semantic Kernel | Tool orchestration                          | Tools, Multi-turn                      | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/semantickernel) |
| 🐍 Python  | AG2             | Mutual agent calls                          | Agent-to-Agent communication          | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/ag2) |
| 🐍 Python  | Azure AI Foundry| Azure AI integration                        | Cloud deployment, Tools               | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/azureaifoundry_sdk) |
| 🐍 Python  | LlamaIndex      | File Q&A retrieval                          | RAG, Document processing              | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/python/agents/llama_index_file_chat) |
| 🚀 JS/TS   | Genkit          | Movie info / Code generation                | Tools, Artifacts (Files), Async       | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/js/src/agents)          |
| ☕ Java    | Spring Boot     | Multi-transport agent                       | HTTP/gRPC, Security                   | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/java/agents/dice_agent_multi_transport) |
| 💠 .NET    | Semantic Kernel | .NET AI integration                         | Tools, .NET ecosystem                 | [Link](https://github.com/a2aproject/a2a-samples/tree/main/samples/dotnet/A2ASemanticKernelDemo) |

#### Community Implementations

##### SDKs & Libraries (by language)

*   **Go**
    *   🌟 [a2a-go](https://github.com/a2aproject/a2a-go) by [@a2aproject](https://github.com/a2aproject) [![Stars](https://img.shields.io/github/stars/a2aproject/a2a-go?style=social)](https://github.com/a2aproject/a2a-go) - **Official** Go SDK for the A2A Protocol with high-level server (`a2asrv`) and client (`a2aclient`) APIs, multi-transport support (gRPC, REST, JSON-RPC), extensible architecture, and a CLI tool for agent discovery and messaging.
    *   🌟 [trpc-a2a-go](https://github.com/trpc-group/trpc-a2a-go) by [@trpc-group](https://github.com/trpc-group) [![Stars](https://img.shields.io/github/stars/trpc-group/trpc-a2a-go?style=social)](https://github.com/trpc-group/trpc-a2a-go) - Go A2A implementation by the tRPC team featuring full client/server support, in-memory task management, streaming responses, session management, multiple auth methods (JWT, API Key, OAuth2), and comprehensive examples.
    *   🌟 [a2a-go](https://github.com/a2aserver/a2a-go) by [@a2aserver](https://github.com/a2aserver) [![Stars](https://img.shields.io/github/stars/a2aserver/a2a-go?style=social)](https://github.com/a2aserver/a2a-go) - A Go library for building A2A servers, with example implementations.
    *  🌟 [a2a-go](https://github.com/yeeaiclub/a2a-go) by [@yeeaiclub](https://github.com/yeeaiclub) [![Stars](https://img.shields.io/github/stars/yeeaiclub/a2a-go?style=social)](https://github.com/yeeaiclub/a2a-go) - Agent-to-Agent Protocol Implementation for Go, fully supports all methods of the A2A protocol, referring to the official Python SDK implementation.
    *   🌟 [agent-sdk-go](https://github.com/agenticenv/agent-sdk-go) by [@agenticenv](https://github.com/agenticenv) [![Stars](https://img.shields.io/github/stars/agenticenv/agent-sdk-go?style=social)](https://github.com/agenticenv/agent-sdk-go) - Production-grade Go SDK for durable AI agents built on Temporal workflows. Features first-class A2A server/client, MCP, AG-UI streaming, sub-agents, human-in-the-loop, and OpenTelemetry. Survives crashes and deploys automatically.
*   **Rust**
    *   🌟 [a2a-rs](https://github.com/a2aproject/a2a-rs) by [@a2aproject](https://github.com/a2aproject) [![Stars](https://img.shields.io/github/stars/a2aproject/a2a-rs?style=social)](https://github.com/a2aproject/a2a-rs) - **Official** Rust SDK for the A2A Protocol. Workspace-based implementation with core types, async client/server, gRPC/SLIMRPC bindings, SSE streaming, protobuf interop, and a CLI tool.
    *   🌟 [ra2a](https://github.com/qntx/ra2a) by [@qntx](https://github.com/qntx) [![Stars](https://img.shields.io/github/stars/qntx/ra2a?style=social)](https://github.com/qntx/ra2a) - Comprehensive Rust SDK for A2A v1.0 with all 12 JSON-RPC methods, gRPC/SSE streaming, pluggable storage (PostgreSQL/MySQL/SQLite), OAuth 2.0/mTLS security, OpenTelemetry tracing, and composable Axum handlers.
    *   🌟 [a2a-rs](https://github.com/EmilLindfors/a2a-rs) by [@EmilLindfors](https://github.com/EmilLindfors) [![Stars](https://img.shields.io/github/stars/EmilLindfors/a2a-rs?style=social)](https://github.com/EmilLindfors/a2a-rs) - An idiomatic Rust implementation following hexagonal architecture principles.
    *   🌟 [Agentic](https://github.com/jeremychone/rust-agentic) by [@jeremychone](https://github.com/jeremychone) [![Stars](https://img.shields.io/github/stars/jeremychone/rust-agentic?style=social)](https://github.com/jeremychone/rust-agentic) - A Rust crate providing essential building blocks for agentic applications, with an ergonomic API for MCP and A2A support. (Work in Progress)
    *   🌟 [jamjet-a2a](https://github.com/jamjet-labs/jamjet-a2a) by [@jamjet-labs](https://github.com/jamjet-labs) [![Stars](https://img.shields.io/github/stars/jamjet-labs/jamjet-a2a?style=social)](https://github.com/jamjet-labs/jamjet-a2a) - Standalone Rust SDK for A2A v1.0 with client, server, coordinator routing, and MCP bridge. TCK conformant (75/76 mandatory). Two crates: `jamjet-a2a-types` (pure types, zero I/O) + `jamjet-a2a` (full SDK with feature flags).
    *   🌟 [a2a-rust](https://github.com/tomtom215/a2a-rust) by [@tomtom215](https://github.com/tomtom215) - Pure Rust SDK for A2A v1.0 with quad transport (JSON-RPC/REST/WebSocket/gRPC), SSE streaming, agent card signing (JWS/ES256), pluggable stores (SQLite/PostgreSQL), multi-tenancy, and TCK conformance. Published on crates.io as `a2a-protocol-sdk`.
    *   🌟 [awaken](https://github.com/awakenworks/awaken) by [@awakenworks](https://github.com/awakenworks) [![Stars](https://img.shields.io/github/stars/awakenworks/awaken?style=social)](https://github.com/awakenworks/awaken) - A Rust agent runtime that serves AI SDK, CopilotKit, A2A, and MCP from the same backend, featuring type-safe state, streaming LLM failure recovery, and plugin extensibility. Published on crates.io.
    *   🌟 [turul-a2a](https://github.com/aussierobots/turul-a2a) by [@aussierobots](https://github.com/aussierobots) [![Stars](https://img.shields.io/github/stars/aussierobots/turul-a2a?style=social)](https://github.com/aussierobots/turul-a2a) - Proto-first Rust SDK for A2A v1.0 with ergonomic server/client crates, pluggable storage (SQLite/PostgreSQL/DynamoDB), multi-transport support (HTTP/JSON-RPC/SSE/gRPC/AWS Lambda), JWT/API-key auth, and interoperability-tested against the official Go SDK. Published on crates.io.
*   **Python**
    *   🌟 [a2a-python](https://github.com/a2aproject/a2a-python) by [@a2aproject](https://github.com/a2aproject) [![Stars](https://img.shields.io/github/stars/a2aproject/a2a-python?style=social)](https://github.com/a2aproject/a2a-python) - **Official** Python SDK for running agentic applications as A2A servers following the Agent2Agent Protocol.
    *   🌟 [a2a_min](https://github.com/pcingola/a2a_min) by [@pcingola](https://github.com/pcingola) [![Stars](https://img.shields.io/github/stars/pcingola/a2a_min?style=social)](https://github.com/pcingola/a2a_min) - A minimalistic Python SDK for A2A communication.
    *   🌟 [python-a2a](https://github.com/themanojdesai/python-a2a) by [@themanojdesai](https://github.com/themanojdesai) [![Stars](https://img.shields.io/github/stars/themanojdesai/python-a2a?style=social)](https://github.com/themanojdesai/python-a2a) - An easy-to-use Python library for implementing the A2A protocol.
    *   🌟 [fasta2a](https://github.com/datalayer/fasta2a) by [@datalayer](https://github.com/datalayer) [![Stars](https://img.shields.io/github/stars/datalayer/fasta2a?style=social)](https://github.com/datalayer/fasta2a) - Framework-agnostic Python A2A server library that lets developers expose agents through ASGI with pluggable storage, broker, and worker components.
    *   🌟 [A2AServer](https://github.com/johnson7788/A2AServer) by [@johnson7788](https://github.com/johnson7788) [![Stars](https://img.shields.io/github/stars/johnson7788/A2AServer?style=social)](https://github.com/johnson7788/A2AServer) - A Python server framework implementing Google's A2A protocol with MCP integration.
    *   🌟 [adk-modular-architecture](https://github.com/k-jarzyna/adk-modular-architecture) by [@k-jarzyna](https://github.com/k-jarzyna) [![Stars](https://img.shields.io/github/stars/k-jarzyna/adk-modular-architecture?style=social)](https://github.com/k-jarzyna/adk-modular-architecture) - A Python project demonstrating a modular architecture for ADK (Agent Development Kit) based agents, with A2A protocol considerations.
    *   🌟 [codex-a2a](https://github.com/liujuanjuan1984/codex-a2a) by [@liujuanjuan1984](https://github.com/liujuanjuan1984) [![Stars](https://img.shields.io/github/stars/liujuanjuan1984/codex-a2a?style=social)](https://github.com/liujuanjuan1984/codex-a2a) - Full A2A Protocol implementation for Codex CLI, providing a stateful, production-oriented agent service with standardized transport and lifecycle mapping.
    *   🌟 [opencode-a2a](https://github.com/Intelligent-Internet/opencode-a2a) by [@Intelligent-Internet](https://github.com/Intelligent-Internet) [![Stars](https://img.shields.io/github/stars/Intelligent-Internet/opencode-a2a?style=social)](https://github.com/Intelligent-Internet/opencode-a2a) - Full A2A Protocol implementation for OpenCode, providing a stateful A2A service with production-friendly deployment, auth, and session continuity.
    *   🌟 [a2a-adapter](https://github.com/hybroai/a2a-adapter) by [@hybroai](https://github.com/hybroai) [![Stars](https://img.shields.io/github/stars/hybroai/a2a-adapter?style=social)](https://github.com/hybroai/a2a-adapter) - Python SDK that converts agents from n8n, LangGraph, CrewAI, LangChain, Claude Code, Codex, Ollama, and more into A2A-compatible servers with auto-generated AgentCards and streaming support. Published on PyPI.
    *   🌟 [distributed_a2a](https://github.com/Barra-Technologies/distributed_a2a) by [@Barra-Technologies](https://github.com/Barra-Technologies) [![Stars](https://img.shields.io/github/stars/Barra-Technologies/distributed_a2a?style=social)](https://github.com/Barra-Technologies/distributed_a2a) - A Python library for building and orchestrating A2A agents with a registry service, router agent, routing client, and MCP management. MIT licensed and published on PyPI as `distributed-a2a`.
*   **Ruby**
    *   🌟 [a2a](https://github.com/wilsonsilva/a2a) by [@wilsonsilva](https://github.com/wilsonsilva) [![Stars](https://img.shields.io/github/stars/wilsonsilva/a2a?style=social)](https://github.com/wilsonsilva/a2a) - Ruby gem implementing A2A protocol data structures with serialization, validation, and case transformation support. Published on RubyGems.
    *   🌟 [llm.rb](https://github.com/llmrb/llm.rb) by [@llmrb](https://github.com/llmrb) [![Stars](https://img.shields.io/github/stars/llmrb/llm.rb?style=social)](https://github.com/llmrb/llm.rb) - Ruby's most capable AI runtime with A2A support via `LLM::A2A`, letting agents consume remote A2A agent skills as local tools over REST/JSON-RPC. Licensed under 0BSD.
    *   🌟 [agent2agent](https://github.com/general-intelligence-systems/agent2agent) by [@general-intelligence-systems](https://github.com/general-intelligence-systems) [![Stars](https://img.shields.io/github/stars/general-intelligence-systems/agent2agent?style=social)](https://github.com/general-intelligence-systems/agent2agent) - Full-featured Ruby SDK for A2A with server and client implementations, JSON-RPC 2.0 and HTTP+JSON/REST bindings, SSE streaming, SQLite persistence, push notifications, 47 protocol types, and extensive guides. Built on Falcon + Async for fiber-based concurrency. Published on RubyGems as `agent2agent`. Apache 2.0.
*   **C++**
    *   🌟 [agent-protocol](https://github.com/openJiuwen-ai/agent-protocol) by [@openJiuwen-ai](https://github.com/openJiuwen-ai) [![Stars](https://img.shields.io/github/stars/openJiuwen-ai/agent-protocol?style=social)](https://github.com/openJiuwen-ai/agent-protocol) - C++ SDK for the Agent2Agent (A2A) Protocol (and MCP), providing implementations of agent communication protocols for C++ environments.
    *   🌟 [a2a-cpp](https://github.com/MisterVVP/a2a-cpp) by [@MisterVVP](https://github.com/MisterVVP) [![Stars](https://img.shields.io/github/stars/MisterVVP/a2a-cpp?style=social)](https://github.com/MisterVVP/a2a-cpp) - C++20 SDK for the Agent2Agent (A2A) Protocol with client/server APIs, discovery, REST/JSON-RPC/gRPC transports, streaming, authentication hooks, and CMake/vcpkg/Conan build integration.
*   **Common Lisp**
    *   🌟 [mcp-lisp](https://github.com/jsulmont/mcp-lisp) by [@jsulmont](https://github.com/jsulmont) [![Stars](https://img.shields.io/github/stars/jsulmont/mcp-lisp?style=social)](https://github.com/jsulmont/mcp-lisp) - Common Lisp SDK for MCP and A2A protocols with server, client, agent, and behavioral spec engine. Implements partial A2A v1.0 support (agent card discovery, messaging, skills, and task lifecycle). Features 438 unit tests, REPL agent with multi-provider LLM support, and agent swarm capabilities. Dual-licensed under MIT OR Apache-2.0.
*   **C#/.NET**
    *   🌟 [a2a-dotnet](https://github.com/a2aproject/a2a-dotnet) by [@a2aproject](https://github.com/a2aproject) [![Stars](https://img.shields.io/github/stars/a2aproject/a2a-dotnet?style=social)](https://github.com/a2aproject/a2a-dotnet) - **Official** C#/.NET SDK for the A2A Protocol.
    *   🌟 [a2adotnet](https://github.com/azixaka/a2adotnet) by [@azixaka](https://github.com/azixaka) [![Stars](https://img.shields.io/github/stars/azixaka/a2adotnet?style=social)](https://github.com/azixaka/a2adotnet) - A C#/.NET implementation of the A2A protocol.
    *   🌟 [a2a-net](https://github.com/neuroglia-io/a2a-net) by [@neuroglia-io](https://github.com/neuroglia-io) [![Stars](https://img.shields.io/github/stars/neuroglia-io/a2a-net?style=social)](https://github.com/neuroglia-io/a2a-net) - .NET implementation of the Agent2Agent (A2A) protocol to enable secure, interoperable communication between autonomous agents across frameworks and vendors.
*   **JavaScript/TypeScript**
    *   🌟 [a2a-js](https://github.com/a2aproject/a2a-js) by [@a2aproject](https://github.com/a2aproject) [![Stars](https://img.shields.io/github/stars/a2aproject/a2a-js?style=social)](https://github.com/a2aproject/a2a-js) - **Official** JavaScript SDK for the Agent2Agent (A2A) Protocol.
    *   🌟 [a2a-ai-provider](https://github.com/DracoBlue/a2a-ai-provider) by [@DracoBlue](https://github.com/DracoBlue) [![Stars](https://img.shields.io/github/stars/DracoBlue/a2a-ai-provider?style=social)](https://github.com/DracoBlue/a2a-ai-provider) - Community A2A provider for the Vercel AI SDK, enabling drop-in interoperability with A2A agents via `generateText` and `streamText`.
    *   🌟 [nestjs-a2a](https://github.com/thestupd/nestjs-a2a) by [@thestupd](https://github.com/thestupd) [![Stars](https://img.shields.io/github/stars/thestupd/nestjs-a2a?style=social)](https://github.com/thestupd/nestjs-a2a) - A module for integrating the A2A protocol into NestJS applications.
    *   🌟 [Artinet SDK](https://github.com/the-artinet-project/artinet-sdk) by [@the-artinet-project](https://github.com/the-artinet-project) [![Stars](https://img.shields.io/github/stars/the-artinet-project/artinet-sdk?style=social)](https://github.com/the-artinet-project/artinet-sdk) - TypeScript (Node.js) A2A compliant server/client simplifying interoperable AI agent creation, focusing on DX and production-readiness.
    *   🌟 [a2a-mesh](https://github.com/oaslananka/a2a-mesh) by [@oaslananka](https://github.com/oaslananka) [![Stars](https://img.shields.io/github/stars/oaslananka/a2a-mesh?style=social)](https://github.com/oaslananka/a2a-mesh) - Production-ready TypeScript runtime for Google's A2A Protocol with multi-framework adapters, registry control plane, JWT/API-key auth, OpenTelemetry observability, CLI scaffolding, and testing toolkit. Published on npm.
    *   🌟 [a2a-warp](https://github.com/oaslananka/a2a-warp) by [@oaslananka](https://github.com/oaslananka) [![Stars](https://img.shields.io/github/stars/oaslananka/a2a-warp?style=social)](https://github.com/oaslananka/a2a-warp) - Independent TypeScript runtime and toolkit for the A2A protocol, with server/client SDKs, registry, adapters for OpenAI/Anthropic/LangChain/Google ADK/LlamaIndex/CrewAI, CLI, MCP bridge, WebSocket/gRPC transports, and conformance tooling. Published on npm as `@oaslananka/a2a-warp`. Apache 2.0.
    *   🌟 [a2a-reference-ts](https://github.com/reaatech/a2a-reference-ts) by [@reaatech](https://github.com/reaatech) [![Stars](https://img.shields.io/github/stars/reaatech/a2a-reference-ts?style=social)](https://github.com/reaatech/a2a-reference-ts) - Production-ready TypeScript reference implementation of Google's A2A protocol with server framework (Express/Hono adapters), client SDK, bidirectional A2A ↔ MCP bridge, canonical Zod schemas, pluggable auth (OAuth2/JWT/API key), Redis/Postgres persistence, SSE streaming, and OpenTelemetry observability. Published on npm as `@reaatech/*`.
    *   🌟 [agent-to-agent-ts](https://github.com/A2A-tools/agent-to-agent-ts) by [@A2A-tools](https://github.com/A2A-tools) [![Stars](https://img.shields.io/github/stars/A2A-tools/agent-to-agent-ts?style=social)](https://github.com/A2A-tools/agent-to-agent-ts) - Practical TypeScript A2A implementation with gRPC-first transport, AgentCard discovery, task lifecycle management, JSON Schema validation, HTTP/WebSocket helpers, and a bundled CLI. Node 22+.
*   **PHP**
    *   🌟 [a2a-php](https://github.com/andreibesleaga/a2a-php) by [@andreibesleaga](https://github.com/andreibesleaga) [![Stars](https://img.shields.io/github/stars/andreibesleaga/a2a-php?style=social)](https://github.com/andreibesleaga/a2a-php) - PHP implementation of the A2A Protocol with a fully compliant reference server, strict JSON-RPC validation, task management, SSE streaming, push notifications, and 100% official TCK pass rate.
*   **Java**
    *   🌟 [a2a-java](https://github.com/a2aproject/a2a-java) by [@a2aproject](https://github.com/a2aproject) [![Stars](https://img.shields.io/github/stars/a2aproject/a2a-java?style=social)](https://github.com/a2aproject/a2a-java) - **Official** Java SDK for the Agent2Agent (A2A) Protocol.
    *   🌟 [a2a-jakarta](https://github.com/wildfly-extras/a2a-jakarta) by [@wildfly-extras](https://github.com/wildfly-extras) [![Stars](https://img.shields.io/github/stars/wildfly-extras/a2a-jakarta?style=social)](https://github.com/wildfly-extras/a2a-jakarta) - Jakarta EE integration for the A2A Java SDK, implementing A2A Protocol Specification 1.0 on WildFly, Tomcat, Jetty, and OpenLiberty. Apache 2.0.
    *   🌟 [a2ajava](https://github.com/vishalmysore/a2ajava) by [@vishalmysore](https://github.com/vishalmysore) [![Stars](https://img.shields.io/github/stars/vishalmysore/a2ajava?style=social)](https://github.com/vishalmysore/a2ajava) - Java A2A server/client implementation using Spring Boot with annotations. Supports WebSockets, MCP integration, and includes enterprise/Kubernetes deployment tutorials.
    *   🌟 [a2a4j](https://github.com/a2ap/a2a4j) by [@a2ap](https://github.com/a2ap) [![Stars](https://img.shields.io/github/stars/a2ap/a2a4j?style=social)](https://github.com/a2ap/a2a4j) - A2A4J is a comprehensive Java implementation of the Agent2Agent Protocol, including server, client, examples, and a starter — ready to use out of the box.
    *   🌟 [spring-ai-a2a](https://github.com/spring-ai-community/spring-ai-a2a) by [@spring-ai-community](https://github.com/spring-ai-community) [![Stars](https://img.shields.io/github/stars/spring-ai-community/spring-ai-a2a?style=social)](https://github.com/spring-ai-community/spring-ai-a2a) - Spring Boot and Spring AI integration for building AI agent servers using the A2A Protocol. Features auto-configuration, full `@Tool` support, and multi-agent orchestration examples.
    *   🌟 [rocketmq-a2a](https://github.com/apache/rocketmq-a2a) by [@apache](https://github.com/apache) [![Stars](https://img.shields.io/github/stars/apache/rocketmq-a2a?style=social)](https://github.com/apache/rocketmq-a2a) - Apache RocketMQ transport integration for the A2A Protocol. Provides `RocketMQTransport` for asynchronous client messaging and `RocketMQA2AServerRoutes` for Quarkus server-side routing, with samples for Google ADK, AgentScope, and LangGraph. Apache 2.0.
*   **Kotlin**
    *   🌟 [a2a-4k](https://github.com/a2a-4k/a2a-4k) by [@a2a-4k](https://github.com/a2a-4k) [![Stars](https://img.shields.io/github/stars/a2a-4k/a2a-4k?style=social)](https://github.com/a2a-4k/a2a-4k) - Kotlin implementation of the A2A protocol with client/server modules, Ktor-based server support, Redis-backed task storage, streaming support, and examples for Arc and LangChain4j integrations.
*   **Swift**
    *   🌟 [a2a-swift](https://github.com/Victory-Apps/a2a-swift) by [@Victory-Apps](https://github.com/Victory-Apps) [![Stars](https://img.shields.io/github/stars/Victory-Apps/a2a-swift?style=social)](https://github.com/Victory-Apps/a2a-swift) - A Swift SDK for A2A with full v1.0 data model, JSON-RPC routing, SSE streaming with reconnection