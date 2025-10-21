# AI Email Response Writer

## Project Overview
**AI Email Response Writer** is a Python-based AI tool designed to help automate professional email responses. The application uses a **node-based workflow** built with **LangGraph**, enabling structured, multi-step processing with AI assistance, memory storage, tool integration, and human approval.

The system interacts with the **Google Generative AI (Gemini)** model for drafting and improving emails and supports **human-in-the-loop (HITL)** validation to ensure quality.

---

## Features
- Generate professional, polite email replies using **Gemini-2.0 AI**.
- Grammar and tone checking via AI-assisted **Tool Node**.
- Memory storage of past emails for context and reference.
- Human approval workflow for quality assurance.
- Conditional branching for low-quality drafts to retry AI generation.
- Node-based architecture for modular and extensible workflows.

---

## Node Architecture

The workflow is modeled as a **graph of nodes**:

1. **Input Node**
   - Captures the incoming email from the user.
   - Initializes the email state.

2. **LLM Node**
   - Generates the initial draft response using the Gemini model.

3. **Tool Node**
   - Reviews and corrects grammar, tone, and clarity of the draft.

4. **Conditional Node** (integrated with Tool Node)
   - Evaluates the draft quality and decides whether to retry LLM or save to memory.

5. **Memory Node**
   - Saves the email draft and related state to `email_memory.json`.

6. **Human-in-the-Loop (HITL) Node**
   - Allows a human to approve, reject, or manually edit the draft.

7. **UI Output Node**
   - Displays the final approved email response.

**Workflow Diagram (simplified):**

Input → LLM → Tool → Conditional → Memory → HITL → UI


---

## Technologies & Libraries
- **Python 3.12.4**
- **LangGraph** – For stateful, multi-step AI workflows.
- **LangChain Core** – Structured messages (`HumanMessage`, `AIMessage`).
- **Google Generative AI (Gemini)** – Core AI model for email generation.
- **dotenv** – Secure API key management.
- **JSON** – Storage of past emails and drafts.

---

## Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/mntc3434/Email-Response-Writer.git
cd Email-Response-Writer
