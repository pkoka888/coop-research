Ollama CLI – Study

Install/Update
- Windows/Mac/Linux installers at ollama.com; update via installer or `ollama update`.

Usage
- Pull model: `ollama pull llama3`
- Run prompt: `ollama run llama3` (interactive)
- Pipe prompt: `type prompt.txt | ollama run llama3`

Project-local
- Models and modelfiles can be stored in repo; run with explicit `-m` or model name.

Integration
- Good for local embeddings or inference as part of indexing pipelines.

Pitfalls
- GPU/CPU resource constraints; versioned models recommended.

Embeddings + Qdrant Pipeline (Local)
- Pull embedding model: `ollama pull nomic-embed-text`
- Generate embeddings (example): `type file.txt | ollama run nomic-embed-text > embeds.json`
- Upsert to Qdrant: use `qdrant-client` (Python) or HTTP API; store `{id, vector, payload:{filepath, sha}}`
- Index maintenance: run a watcher to re-embed on file change; batch periodically.

Modelfiles
- Customize prompts or defaults via a `Modelfile`, then `ollama create my-model -f Modelfile`.

