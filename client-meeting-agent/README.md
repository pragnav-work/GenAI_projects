# Client Meeting Preparation Agent

An AI-powered meeting preparation agent that gathers relevant information from client documents, previous meeting notes, and persistent memory to generate a concise meeting brief.

## Objective

The goal of this project is to build an agentic AI system that can prepare a manager for an upcoming client meeting by combining:

* Retrieval-Augmented Generation (RAG)
* Vector search
* Short-term conversation memory
* Long-term persistent memory
* Agentic reasoning and tool usage

The agent is designed to go beyond simple question answering by deciding which information it needs, using the appropriate tools, and combining the retrieved information into a final meeting brief.

## Architecture

```text
User Request
     ↓
AI Agent
     ↓
Reason → Act → Observe
     ↓
┌───────────────────────────────┐
│ Client Document Search        │
│ Meeting Notes Search          │
│ Long-Term Memory Search       │
└───────────────────────────────┘
     ↓
Retrieved Context
     ↓
Meeting Brief
```

## Key Features

### RAG and Vector Search

Client documents and previous meeting notes are loaded, split into chunks, converted into embeddings, and stored in FAISS for semantic retrieval.

The agent can retrieve relevant information based on meaning rather than relying only on exact keyword matches.

### Short-Term Memory

The current conversation and tool observations are maintained in the agent's history.

This allows the agent to use information retrieved during earlier steps when deciding what to do next.

### Long-Term Memory

Important information is stored in a persistent memory file and represented as embeddings in a FAISS index.

This allows relevant information to be retrieved across different sessions.

### Agentic Workflow

The agent follows a ReAct-style workflow:

```text
Reason → Act → Observe
```

The agent determines what information is required, selects an appropriate tool, observes the result, and continues until it can produce the final answer.

A maximum iteration limit is used to prevent the agent from running indefinitely.

## Tools

The agent uses three tools:

1. **Client Document Search**

   * Retrieves relevant information from client documents.

2. **Meeting Notes Search**

   * Retrieves information from previous client meetings, including discussions and action items.

3. **Long-Term Memory Search**

   * Retrieves relevant information stored across previous sessions.

## Project Structure

```text
client-meeting-agent/
│
├── data/
│   ├── client_documents/
│   │   ├── client_profile.txt
│   │   ├── company_overview.txt
│   │   └── project_details.txt
│   │
│   ├── meeting_notes/
│   │   ├── meeting_2026_06_10.txt
│   │   ├── meeting_2026_07_15.txt
│   │   └── meeting_2026_08_12.txt
│   │
│   └── memory/
│       └── long_term_memory.txt
│
├── notebooks/
│   └── Client_Meeting_Agent.ipynb
│
├── screenshots/
│
├── README.md
└── requirements.txt
```

## Example

### User Request

> Prepare me for my meeting with Acme Corp.

### Agent Workflow

The agent retrieves:

* Client profile and company information
* Current project details and requirements
* Previous meeting discussions
* Pending action items
* Relevant long-term memories

It then combines the retrieved context and generates a concise meeting brief containing key information, discussion points, open items, and suggested next steps.

## Technologies Used

* Python
* Jupyter Notebook
* Sentence Transformers
* FAISS
* NumPy
* Google Gemini
* Python standard libraries

## Setup

Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Configure the required Gemini API key using the environment configuration used by the notebook.

## Running the Project

Open the notebook:

```text
notebooks/Client_Meeting_Agent.ipynb
```

Run the cells sequentially to:

1. Load the client documents and meeting notes.
2. Create document chunks.
3. Generate embeddings.
4. Build the FAISS vector indexes.
5. Configure short-term and long-term memory.
6. Define the agent tools.
7. Run the ReAct agent.
8. Generate the final meeting brief.

## Assignment Requirements Covered

| Requirement       | Implementation                          |
| ----------------- | --------------------------------------- |
| RAG               | FAISS-based semantic retrieval          |
| Vector Database   | FAISS                                   |
| Short-Term Memory | Agent conversation history              |
| Long-Term Memory  | Persistent memory file + FAISS          |
| Agentic Workflow  | ReAct-style Reason → Act → Observe loop |
| 2–3 Tools         | Three retrieval tools                   |
| Meeting Brief     | Generated from retrieved information    |
| Sample Data       | Client documents and meeting notes      |
| Source Code       | Jupyter Notebook                        |
| Documentation     | README.md                               |
| Screenshots       | `screenshots/`                          |

## Limitations

This project is designed as a demonstration of RAG, memory, tool usage, and agentic workflows. The sample data is local and limited to a small set of client documents and meeting notes.

For a production system, the same architecture could be extended with live enterprise data sources such as email, CRM systems, calendars, and document management platforms.
