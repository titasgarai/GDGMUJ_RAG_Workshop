# 🚀 Multi-PDF Retrieval-Augmented Generation (RAG) Chatbot

[![Colab](https://img.shields.io/badge/Run%20in-Colab-orange?logo=googlecolab&style=flat-square)](https://colab.research.google.com/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&style=flat-square)](https://www.python.org/)
[![Groq](https://img.shields.io/badge/LLM-Groq%20API-green?style=flat-square)](https://groq.com/)
[![GDG MUJ](https://img.shields.io/badge/GDG%20on%20Campus-MUJ-red?style=flat-square)](https://gdg.community.dev/)

An advanced, production-ready Multi-PDF Retrieval-Augmented Generation (RAG) pipeline designed for **GDG on Campus, Manipal University Jaipur (GDG MUJ)**. This repository hosts a fully structured, end-to-end interactive workshop chatbot capable of reading, processing, indexing, and intelligently querying multiple user-uploaded PDF files—even scanned or image-based layouts (via automated OCR fallback).

---

## 🛠️ Key Architectural Highlights

```
                                    [ User Question ]
                                            │
                                    ┌───────┴───────┐
                                    ▼               ▼
                              [BM25 Search]   [Dense Embeddings]
                                    │               │
                                    └───────┬───────┘
                                            ▼
                              [Reciprocal Rank Fusion (RRF)]
                                            │
                                            ▼
                                  [Top-K Citations Ranked]
                                            │
                                            ▼
                                  [LLM Grounded Synthesis]
```

- **Multi-Document Ingestion & Parsing**: Parses structural and textual elements from multiple concurrent PDF inputs using PyMuPDF.
- **Adaptive Tesseract OCR Fallback**: Safely scans and extracts text from image-only PDFs, scanned notes, or digital slides.
- **Smart Chunking & Context Wrapping**: Implements sliding window word-chunking alongside dynamic document headers to protect cross-document context from dilution.
- **Hybrid Dense-Sparse Retrieval**: Combines state-of-the-art vector similarity embeddings (`all-MiniLM-L6-v2`) with custom classical Lexical Token Search (BM25).
- **Reciprocal Rank Fusion (RRF)**: Merges keyword constraints with semantic features using a robust reciprocal ranking index.
- **LLM Grounded Synthesis & Citations**: Directs Groq API's ultra-fast models to synthesize fully referenced outputs complete with bracketed source index citations (`[S1]`, `[S2]`).

---

## 📦 Directory Structure

```bash
├── RAG_Workshop_Notebook.ipynb               # Dynamic interactive Colab notebook
├── README.md                                 # Professional project documentation
├── 01_RAG_Workshop_Event_Details.pdf         # Resource: Event details and timeline
├── 02_RAG_Workshop_Guidelines_and_Rules.pdf  # Resource: Rules, requirements and dress codes
└── 03_GDG_MUJ_Past_Events.pdf                # Resource: Summary and history of GDG MUJ events
```

---

## 🚀 How to Get Started

1. **Run in Google Colab**: Load the `RAG_Workshop_Notebook.ipynb` directly in Colab.
2. **Configure your API Secrets**: 
   - Obtain a free API key from [Console Groq](https://console.groq.com/).
   - Save it inside your Google Colab left sidebar secrets manager ("🔑 icon") with the name `GROQ_API_KEY` and enable access.
3. **Upload Workshop PDFs**: Run Step 4 in the notebook to upload the resource PDF files included in this repository.
4. **Explore & Chat**: Run the comparison cells to observe LLM-only hallucinations vs. verified, cited RAG responses!

---

## 🤝 Contributions
Developed and configured under the **Google Developer Groups on Campus - Manipal University Jaipur**. Feel free to fork, open pull requests, and contribute to optimizing our hybrid retrieval index!
