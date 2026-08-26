# Mini RAG Chatbot

A simple Retrieval-Augmented Generation (RAG) chatbot that answers questions using information retrieved from a PDF document.

## Project Objective

The goal of this project is to implement a complete RAG pipeline:

PDF → Text Extraction → Text Chunking → Embeddings → FAISS → Semantic Search → Context Retrieval → Gemini LLM → Answer

## Technologies Used

- Python
- Jupyter Lab
- PyPDF
- LangChain Text Splitter
- Sentence Transformers
- FAISS
- Google Gemini API

## RAG Pipeline

1. Extract text from the PDF using PyPDF.
2. Split the extracted text into smaller chunks using `RecursiveCharacterTextSplitter`.
3. Convert the chunks into numerical embeddings using Sentence Transformers.
4. Store the embeddings in a FAISS vector index.
5. Convert the user's question into an embedding.
6. Retrieve the most semantically similar chunks using FAISS.
7. Pass the retrieved context and question to Gemini.
8. Generate the final answer using the retrieved context.

## Project Structure

```text
mini-rag-chatbot/
│
├── Mini_RAG_Chatbot.ipynb
├── requirements.txt
├── sample_data/
│   └── sample.pdf
└── screenshots/
│   └── Output1.png
    └── Output2.png


