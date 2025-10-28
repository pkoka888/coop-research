Claude Code CLI – Debug/Setup Study

Scope
- How to run and debug Claude Code CLI reliably per project.
- How to update/reinstall, use project-local settings, and integrate plugins/MCP.

Installation and Update
- Prefer project‑local execution: `npx claude` (keeps config and dependencies near the repo).
- Update paths:
  - `npx claude update` – updates the local CLI install.
  - `npx claude install stable|latest|<version>` – install native build version.
- Fallback binary: if a global `claude` is on PATH, ensure it’s Anthropic’s CLI (supports `-p/--print`).

Execution Modes
- Interactive session (default): `npx claude`.
- Non‑interactive print: pipe prompt and use `-p`:
  - `Get-Content -Raw <prompt.md> | npx claude -p`
  - Output formats: `--output-format text|json|stream-json`.

Settings and Project‑Local Config
- Sources: `--setting-sources user,project,local` controls which layers to load.
- Project‑local file: `.claude/settings.local.json` (ignored by git) for per‑repo config.
- Direct override: `--settings <file-or-json>` to inject settings explicitly.

Plugins and MCP
- Plugins: manage with `npx claude plugin ...` or `--plugin-dir <paths...>` for per‑session plugins.
- MCP servers: `--mcp-config <configs...>` accepts JSON files/strings; use `--strict-mcp-config` to isolate sources.

Debug Flags
- `--debug [filter]` or `--verbose` for diagnostics.
- `--permission-mode` to adjust edit/plan/accept permissions.
- `--allowed-tools` / `--disallowed-tools` to constrain tool usage.

Known Pitfalls and Fixes
- Using wrong CLI: Some binaries named `claude` don’t support `-f`. Use `-p` and pipe input as shown above.
- Mixed settings: If global config conflicts, prefer `--setting-sources project,local` to focus on repo config.
- Network prompts: `npx` needs network; cache with native `install` if frequently used offline.

Recommended Workflow (Per Project)
1) Keep `.claude/settings.local.json` with repo‑specific configuration (ignored by git).
2) Run `npx claude` from the repo root; prefer `-p` for scripted usage.
3) When orchestrating, pipe `coop/skills/ORCHESTRATOR-PROMPT.md` with `-p`.
4) Use `--setting-sources project,local` so project settings take precedence.

