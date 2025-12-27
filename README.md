# RAG Playground

## Flow

The RAG process typically follows these core stages:

1. Ingestion (The Library)

1) Chunking: Documents (PDFs, Markdown, etc.) are broken into small "chunks"
2) Embedding: Converting chunks into numerical fingerprints.
3) Data Persistance: These are stored in a Vector Database.

2. Retrieval (The Search)

1) Retrieval: When a user asks a question, the system searches the database for the most relevant chunks of text.
2) Re-rank: use cross-encoder (slow but accurent)

3. Generation (The Answer)

1) Context: The system "stuffs" these relevant facts into the prompt, giving the LLM the exact context it needs.
2) Send the prompt to a LLM. The LLM reads the context and generates a response grounded in the provided facts, rather than guessing.

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
