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

