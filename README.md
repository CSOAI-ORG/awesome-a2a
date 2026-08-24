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

*   📖 [A2A Technical Documentation](https://a2aproject.github.io/A2A/#/documentation) - **(Full Details)** Detai