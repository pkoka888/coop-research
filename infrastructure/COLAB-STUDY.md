Google Colab – Study and COOP Integration

What Colab Provides
- Managed Jupyter notebooks with free/paid CPU/GPU/TPU time.
- Easy GitHub/Drive integration and dependency installation.

Considerations
- Free tier has session timeouts and variable GPU availability.
- Storage is ephemeral; persist to Drive or push results back to GitHub.
- Secrets management via environment/Colab UI; avoid committing credentials.

Integration Patterns
1) GitHub‑centric notebooks
   - Store notebooks in `colab/` folder in project or central research repo.
   - Open in Colab directly from GitHub; results saved to Drive or PRs.
2) Data/index pipelines
   - Use Colab to generate embeddings or run experiments; export artifacts (e.g., index files) back to repo.
3) COOP hooks
   - Add a research issue reminding to run Colab experiments monthly.
   - Use `gh` to open/track Colab tasks.

Recommended Setup
- Keep notebooks under version control in the research repo (GitHub is the source of truth).
- Parameterize notebooks (project slug, data path) to reuse across projects.
- Document environment cells (pip installs, CUDA checks) at top.

Limits
- Not a stable production runner; use for research and experiments, not always‑on services.

