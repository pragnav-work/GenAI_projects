# Mini Semantic Search Engine

## Overview

A Python-based semantic search engine implemented using Sentence Transformers and FAISS.

The project converts a domain-specific knowledge base into vector embeddings, stores the embeddings in a FAISS vector index, and retrieves the top three semantically relevant sentences for a given user query.

The implementation demonstrates the retrieval component commonly used in modern RAG and semantic search systems.

## Objective

The objective is to implement a lightweight semantic search pipeline capable of:

- Generating text embeddings
- Storing embeddings in a FAISS vector index
- Performing similarity-based retrieval
- Returning the top three relevant results
- Supporting continuous user queries through an interactive CLI

## Technologies Used

- Python
- NumPy
- Sentence Transformers
- FAISS
- `all-MiniLM-L6-v2`

## Project Structure

```text
mini-semantic-search/
│
├── Mini_Semantic_Search.ipynb
├── README.md
├── theory_answers.md
├── requirements.txt
└── .gitignore