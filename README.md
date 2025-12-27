# RAG Playground

## Flow

The RAG process typically follows these core stages:

1. Ingestion (The Library)

- Chunking: Source documents (PDFs, Markdown files, etc.) are split into smaller, manageable text chunks.
- Embedding: Each chunk is converted into a numerical vector representation that captures its semantic meaning.
- Data Persistance: The resulting embeddings are stored in a vector database for efficient retrieval.

2. Retrieval (The Search)

- Retrieval: When a user asks a question, the system searches the database for the most relevant chunks of text.
- Re-rank: A cross-encoder model is used to re-rank the retrieved chunks for higher accuracy (at the cost of additional latency).

3. Generation (The Answer)

- Context Assembly: The top-ranked chunks are injected into the prompt, providing the LLM with precise, relevant context.
- Response Generation: The LLM uses this grounded context to generate an answer based on the retrieved facts, rather than relying on speculation.

## Set up env

Use `uv` to set up virtual env
```bash
uv init .
```

Install dependency

```bash
uv add --dev ipykernel
```

```bash
uv add sentence_transformers chromadb google-genai python-dotenv
```

- `sentence_transformers`: add `embedding` and `cross-encoder` models
- `chromadb`: vector database
- `google-genai`: Gemini AI SDK
- `python-dotenv`: env var set up

To install dependency

```bash
uv sync
```
