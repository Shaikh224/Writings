# RAG: How AI Uses External Knowledge

Large Language Models (LLMs) are powerful, but they don't automatically know your private or constantly changing data. **Retrieval-Augmented Generation (RAG)** solves this by giving the model relevant information at query time.

## How RAG Works

The basic pipeline is:

```text
Documents
   ↓
Chunking
   ↓
Embeddings
   ↓
Vector Database
   ↓
User Query
   ↓
Similarity Search
   ↓
Relevant Context
   ↓
LLM
   ↓
Answer
```

### 1. Chunking

Documents such as PDFs, websites, or Markdown files are divided into smaller pieces called **chunks**.

### 2. Embeddings

Each chunk is converted into a numerical vector that represents its meaning.

```text
"How do I get a refund?"
        ↓
   Embedding Model
        ↓
[0.21, -0.43, 0.87, ...]
```

### 3. Retrieval

When a user asks a question, the query is also converted into an embedding. The system searches the vector database for the most relevant chunks.

### 4. Generation

The retrieved chunks are added to the LLM's context:

```text
Question + Retrieved Context
            ↓
           LLM
            ↓
          Answer
```

The model can therefore answer using information from your own data.

## Why RAG?

RAG is useful for:

* Company knowledge bases
* PDF/document assistants
* Customer support
* Research assistants
* Documentation search
* AI agents

Unlike fine-tuning, RAG doesn't require retraining the model when your documents change.

## The Important Part

A RAG system isn't just an LLM + vector database.

Poor **chunking** → poor retrieval
Poor **retrieval** → wrong context
Wrong context → unreliable answers

That's why modern RAG systems often use **hybrid search, reranking, metadata filtering, evaluation, and observability**.

> **Good RAG = Good Retrieval + Good Context + Good Generation**

RAG is ultimately about giving an AI system the **right information at the right time**.
