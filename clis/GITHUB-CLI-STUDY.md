GitHub CLI (gh) – Study

Install/Update
- Windows: `winget install GitHub.cli` or `scoop install gh`
- Update: `gh version upgrade`

Auth & Setup
- `gh auth login` (HTTPS + device flow)
- `gh repo create <org/repo> --public --source . --push`

Project-local Usage
- Issues/PRs: `gh issue create`, `gh pr create`
- Actions: `gh workflow run`, `gh run watch`

Integration in COOP
- Use `gh` to publish research docs to a central repository.

Pitfalls
- Requires authentication and scopes; use a fine-grained token in CI where needed.

