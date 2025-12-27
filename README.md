# RAG Playground

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

Start Jupiter Notebook in uv

```bash
uv run --with jupyter jupyter lab
```


