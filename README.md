# Email Response Writer

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

## Workflow Diagram

![screenshot](https://github.com/mntc3434/Email-Respons-Writer/blob/main/Screenshot%202025-10-21%20114616.png)
---

## Technologies & Libraries
- **Python 3.12.4**
- **LangGraph** – For stateful, multi-step AI workflows.
- **LangChain Core** – Structured messages (`HumanMessage`, `AIMessage`).
- **Google Generative AI (Gemini)** – Core AI model for email generation.
- **dotenv** – Secure API key management.
- **JSON** – Storage of past emails and drafts.

---

## How It Works for Users
1. **Receive Email**  
   Users input an incoming email into the system.

2. **AI Draft Generation**  
   The AI (Gemini model) generates a professional draft response based on the input email.

3. **Draft Review & Improvement**  
   The draft is checked for grammar, tone, and clarity through a specialized AI Tool Node.

4. **Quality Evaluation**  
   The system evaluates draft quality. If the draft is low-quality, the AI will retry generation automatically.

5. **Human Approval (Optional)**  
   Users can manually review, approve, edit, or reject the draft to ensure accuracy and appropriateness.

6. **Memory Storage**  
   Approved emails are saved in `email_memory.json` for context and future reference.

7. **Final Output**  
   The final approved email is presented to the user for sending.
## Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/mntc3434/Email-Response-Writer.git
cd Email-Response-Writer
# Install required dependencies
pip install -r requirements.txt
