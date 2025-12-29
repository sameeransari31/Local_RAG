# Local RAG from Scratch

This repository contains a **fully local, end-to-end Retrieval-Augmented Generation (RAG) system built purely from scratch** using Python.
The project focuses on **understanding and implementing core RAG internals**, rather than relying on high-level frameworks or managed services.

All components run **locally**, with **no external APIs**, making the system transparent, customizable, and ideal for learning or experimentation.

---

## What This Project Does

The system allows you to:

1. Ingest raw documents
2. Convert them into vector embeddings
3. Store and retrieve relevant context efficiently
4. Generate grounded answers using a local LLM

All steps are **explicitly implemented**, exposing how RAG works under the hood.

---

## Key Features

* Fully local RAG pipeline (offline)
* End-to-end implementation from scratch
* Custom document ingestion & chunking
* Manual vector similarity search
* Flash Attention implementation for efficient inference
* Modular and extensible architecture
* No LangChain / LlamaIndex abstractions

---

## System Architecture

```
Documents
   ↓
Text Cleaning & Chunking
   ↓
Embedding Generation
   ↓
Vector Store (Local)
   ↓
Similarity Search
   ↓
Context Injection
   ↓
LLM Inference (with Flash Attention)
   ↓
Final Answer
```

---

## Core Components (Implemented from Scratch)

### 1️. Document Ingestion & Chunking

* Raw documents are loaded locally
* Text is cleaned and split into semantically meaningful chunks
* Chunk size and overlap are configurable

This step ensures optimal retrieval quality and efficient embedding generation.

---

### 2️. Embedding Generation

* Text chunks are converted into dense vector representations
* Embeddings are generated locally (no API calls)
* Embedding logic is exposed for easy experimentation

---

### 3. Vector Store (Local)

* Embeddings are stored in a lightweight local structure
* No external vector databases (e.g., Pinecone, FAISS abstractions)
* Designed to be simple, transparent, and hackable

---

### 4️. Similarity Search

* Query embeddings are compared with stored vectors
* Cosine similarity is computed manually
* Top-K relevant chunks are selected dynamically

This forms the **retrieval backbone** of the RAG system.

---

### 5️. Context Construction

* Retrieved chunks are combined into a structured context
* Context is injected into the prompt in a controlled manner
* Prevents hallucinations by grounding responses in retrieved data

---

### 6️. LLM Inference (Local)

The model runs **entirely locally**, without cloud dependencies.

Key optimizations include:

#### Flash Attention (Implemented)

* Custom implementation of **Flash Attention**
* Improves memory efficiency and inference speed
* Reduces attention computation overhead for long contexts

This demonstrates low-level understanding of transformer internals beyond simple model usage.

---

### 7️. Additional Internal Implementations

Along with Flash Attention, the project includes **multiple custom implementations**, such as:

* Manual attention flow handling
* Explicit token and context management
* Custom prompt formatting logic
* Efficient batching and inference control

These choices avoid “black-box” abstractions and keep the system transparent.

---

## Why This Project Matters

Most RAG projects rely heavily on frameworks that hide complexity.
This project is different.

It is designed to:

* Deeply understand how RAG works internally
* Learn performance bottlenecks and optimizations
* Build intuition for production-grade GenAI systems
* Serve as a foundation for advanced RAG, agents, or memory systems

---

## Tech Stack

* **Language:** Python
* **ML / DL:** PyTorch
* **LLM:** Local transformer-based model
* **Optimization:** Flash Attention
* **Storage:** Local vector store
* **Environment:** Fully offline

---

##  How to Run

1. Clone the repository

```bash
git clone https://github.com/sameeransari31/Local_RAG.git
cd Local_RAG
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Run the notebook

```bash
jupyter notebook Local_RAG.ipynb
```

---

## Future Improvements

* Hybrid search (BM25 + vector)
* Persistent vector storage
* Streaming responses
* Multi-document querying
* Agentic extensions

---

## License

Apache License — free to use, modify, and learn from.

---

### Final Note

This repository is intentionally built **from scratch** to prioritize **learning, control, and performance understanding** over convenience.

If you’re interested in RAG internals, LLM optimization, or building production-ready GenAI systems, this project is a solid foundation.

---

If you want, next I can:

* Tighten this README for **recruiter impact**
* Add **architecture diagrams**
* Convert this into **resume bullets**
* Write a **LinkedIn post** announcing this project

Just tell me
