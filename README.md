SummerlyAI --  SummerlyAI  is an Application that analyzes the Documents , Videos and Scripts you offer to summarize and suggest About the Documents.
<div align="center">

# Gmail AI Assistant  
### Local-first Gmail auto-reply drafts with RAG (Ollama + Milvus)

<p>
  <img alt="Python" src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" />
  <img alt="Status" src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" />
  <img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge" />
</p>

<p>
  <b>Read emails → Embed → Store in Milvus → Retrieve context → Draft a smart reply (human-in-the-loop)</b>
</p>

</div>

---

## Preview
- Draft replies with context from similar past emails.
- Runs locally (privacy-friendly), saves output as drafts for review.

---

## Features
- Gmail email reader (fetch + parse).
- Vector embeddings + semantic search (Milvus).
- Local LLM reply drafting (Ollama).
- Modular pipeline (easy to swap models / prompts / storage).

---

## Architecture
```mermaid
flowchart LR
  A[Gmail Inbox] --> B[read_gmail.py]
  B --> C[Clean + Chunk]
  C --> D[embedder.py (Embeddings)]
  D --> E[Milvus (vector_store.py)]
  A --> F[New Email]
  F --> G[Retrieve Similar (Milvus)]
  E --> G
  G --> H[smart_reply.py (Ollama)]
  H --> I[Gmail Draft Reply]
