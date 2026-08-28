# GenAI Projects

A collection of hands-on Generative AI and information retrieval projects implemented in Python.

The projects focus on understanding and implementing core components used in modern AI systems, including Retrieval-Augmented Generation (RAG), text embeddings, vector databases, semantic search, and Large Language Models.

## Projects

### 1. Mini RAG Chatbot

A Retrieval-Augmented Generation chatbot that retrieves relevant information from a PDF document and uses Google Gemini to generate answers based on the retrieved context.

**Key concepts:**
- PDF text extraction
- Text chunking
- Text embeddings
- FAISS vector search
- Semantic retrieval
- Context-based question answering
- Gemini LLM integration

[View Mini RAG Chatbot →](./mini-rag-chatbot/)

---

### 2. Mini Semantic Search Engine

A lightweight semantic search engine implemented using Sentence Transformers and FAISS.

The system converts a domain-specific knowledge base into embeddings and retrieves the top three semantically similar sentences for a user query.

**Key concepts:**
- Sentence embeddings
- 384-dimensional vectors
- Vector normalization
- FAISS `IndexFlatL2`
- Similarity search
- Top-K retrieval
- Interactive CLI

[View Mini Semantic Search →](./mini-semantic-search/)

---

## Technologies

- Python
- Jupyter Notebook
- NumPy
- Sentence Transformers
- FAISS
- LangChain
- PyPDF
- Google Gemini API

## Repository Structure

```text
GenAI_projects/
│
├── mini-rag-chatbot/
│   ├── Mini_RAG_Chatbot.ipynb
│   ├── README.md
│   ├── requirements.txt
│   ├── sample_data/
│   │   └── sample.pdf
│   └── screenshots/
│       ├── Output1.png
│       └── Output2.png
│
├── mini-semantic-search/
│   ├── Mini_Semantic_Search.ipynb
│   ├── README.md
│   ├── requirements.txt
│   └── theory_answers.md
│
└── README.md