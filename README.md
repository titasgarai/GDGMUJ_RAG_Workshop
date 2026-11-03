# Multi-PDF Retrieval-Augmented Generation (RAG) Chatbot

This repository contains a complete multi-PDF RAG pipeline built during **The RAG Workshop** for **GDG on Campus, Manipal University Jaipur (GDG MUJ)**.

## Features
- **Multi-PDF Ingestion**: Extract content seamlessly from multiple files.
- **OCR Fallback**: Automated fallback to Tesseract OCR for scanned pages or images.
- **Hybrid Search**: Combines semantic embeddings (via `all-MiniLM-L6-v2`) with keyword-based search (`BM25`) using Reciprocal Rank Fusion (RRF).
- **Query Expansion**: Uses LLMs to generate diverse search terms for better document matching.
- **Grounded Generation**: Produces answers with verifiable source-document citations ([S1], [S2], etc.).

## Setup & Requirements
Make sure to install the required libraries:
```bash
pip install pymupdf sentence-transformers groq pytesseract pillow
```
Set your environment variable `GROQ_API_KEY` before running the chatbot.
