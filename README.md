# Email Response Writer

## Project Overview

**Email Response Writer** is an AI-powered tool designed to automate and assist with email responses. It leverages stateful, multi-step AI workflows using **LangGraph**, enabling structured interaction between AI, tools, memory, and human approval.

The project models the workflow as a **graph of nodes**, where each node performs a specific task in the email generation process.

---

## Features

- AI-based email drafting using **Google Generative AI**.
- Stateful workflow with memory management for context retention.
- Human approval step to ensure quality and relevance.
- Integration with custom tools for enhanced processing.
- Flexible node-based architecture for easy extension.

---

## Architecture

The workflow consists of **6 nodes**:

1. **Input Node** – Captures incoming email or prompt for processing.
2. **LLM Node** – Processes the input using a language model (Google Generative AI).
3. **Tool Node** – Uses external tools for tasks like summarization, formatting, or enrichment.
4. **Memory Node** – Stores and retrieves past interactions for context-aware responses.
5. **Human Approval Node** – Allows a human to review and approve the AI-generated response.
6. **Output Node** – Finalizes and sends the approved email response.

**Graph Workflow:**
