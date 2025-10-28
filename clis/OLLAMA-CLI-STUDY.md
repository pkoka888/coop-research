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

