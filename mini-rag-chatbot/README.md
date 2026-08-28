# Mini RAG Chatbot

## Overview

A simple Retrieval-Augmented Generation (RAG) chatbot that answers questions using information retrieved from a PDF document.

The project implements an end-to-end RAG pipeline, combining document processing, semantic retrieval, vector search, and Large Language Model generation.

## Objective

The objective is to implement a complete RAG workflow in which relevant information is retrieved from a PDF before generating a final response.

### RAG Pipeline

```text
PDF
 ↓
Text Extraction
 ↓
Text Chunking
 ↓
Embeddings
 ↓
FAISS Vector Store
 ↓
Semantic Search
 ↓
Relevant Context
 ↓
Gemini LLM
 ↓
Generated Answer