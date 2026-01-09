# RAG Document Query System (LangChain)

## Problem Statement
Traditional keyword search fails to retrieve semantically relevant information from large document sets. 
This project solves that problem using a Retrieval-Augmented Generation (RAG) pipeline built with LangChain.

---

## System Architecture
![Architecture](assets/rag_architecture.png)

---

## Tech Stack
- Python
- LangChain
- FAISS (Local Vector Store)
- Pinecone (Cloud Vector DB)
- OpenAI Embeddings
- Streamlit

---

## How the System Works
1. Documents are loaded and chunked using recursive text splitters.
2. Each chunk is converted into embeddings.
3. Embeddings are stored in FAISS (local) or Pinecone (cloud).
4. User queries are embedded and matched using semantic similarity.
5. Top-k relevant chunks are passed to the LLM.
6. The LLM generates grounded, context-aware answers.

---

## FAISS vs Pinecone
- FAISS: Fast local testing and experimentation.
- Pinecone: Scalable, production-ready cloud vector search.
This project demonstrates both to compare performance and deployment strategies.

---

## Evaluation & Accuracy
- Tested on real document queries.
- Responses are grounded strictly on retrieved context.
- Observed significant reduction in hallucinations compared to direct LLM prompting.
- Sample outputs are provided in the `outputs/` folder.

---

## How to Run Locally
For FAISS:
```bash
pip install -r requirements.txt
streamlit run rag_faiss_app.py

