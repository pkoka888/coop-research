Claude Code – Project Setup

Steps
1) Create project‑local settings at `.claude/settings.local.json` (ignored by git)
   Example:
   {
     "model": "sonnet",
     "permissionMode": "default",
     "settingSources": ["project", "local"],
     "mcp": {
       "strict": false,
       "configs": []
     },
     "plugins": {
       "dirs": []
     }
   }

2) Run Claude from the project root
   - Interactive: `npx claude`
   - Non‑interactive (print): `Get-Content -Raw coop/skills/ORCHESTRATOR-PROMPT.md | npx claude -p`

3) Optional flags
   - `--setting-sources project,local`
   - `--mcp-config <json-paths>` and `--strict-mcp-config`
   - `--plugin-dir <paths...>` for per‑session plugins

4) Update or install native build
   - `npx claude update`
   - `npx claude install stable|latest`

