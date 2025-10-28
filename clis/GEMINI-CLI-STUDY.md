Gemini CLI – Study

Recommendation: use the universal `llm` CLI with `llm-gemini` plugin for a stable, scriptable Gemini experience.

Install/Update
- `pipx install llm`
- `llm plugins install llm-gemini`
- Update: `llm plugins upgrade llm-gemini`

Project-local Config
- Store API key in environment or llm config.
- For per-repo behavior, keep a `.llmrc` or invoke with explicit flags from scripts.

Usage
- Interactive: `llm -m gemini-pro` (model names vary)
- Print/piped: `type prompt.md | llm -m gemini-pro`
- JSON: `type prompt.md | llm -m gemini-pro --json`

Integrations
- Supports multiple providers via plugins (OpenAI, Anthropic, etc.).

Pitfalls
- Model naming evolves; prefer configurable model alias per repo.
- Rate limits vary by account.

Advanced: Vertex AI vs AI Studio
- AI Studio (API Keys): quickest path; supports text/chat and, if enabled, image generation (Imagen 3). Good for Colab tests.
- Vertex AI (Service Account/GCP Project): enterprise auth, logging, quotas, and regional endpoints. Use for production services.

llm-gemini Configuration
- Set API key: `llm keys set gemini` (stores in llm config)
- Use per-repo alias: create `.llmrc` with `model: gemini-1.5-flash` (or `gemini-1.5-pro`)
- Pipe mode with JSON: `type prompt.md | llm -m gemini-1.5-flash --json`

Rate Limits and Quotas
- AI Studio free tiers have daily limits; check https://ai.google.dev/pricing
- Vertex AI quotas configurable per project/region.

Models (examples)
- Text/Multimodal: `gemini-1.5-flash`, `gemini-1.5-pro`, `gemini-1.5-flash-8b`
- Vision (via multimodal) and image generation (Imagen 3 via AI Studio or Vertex Vision)

Security & Keys
- Never commit keys. Use env vars in CI/Colab or llm’s secure key store locally.

