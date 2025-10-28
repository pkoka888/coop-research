Research Sync – Central GitHub Repo

Goal
- Keep all research docs in a central GitHub repository; each project pushes validated research there.

Workflow
1) Set `research.repoUrl` in `coop/coop-settings.json` (e.g., https://github.com/<org>/coop-research)
2) Validate local research: `coop:research-validate`
3) Sync to central repo: `coop:research-sync`
   - Requires `gh` authenticated or `git` push permissions.
4) Propose structure changes via `gh issue create` on the central repo.

Notes
- Enforce via settings: `enforceGithubOnly: true` to discourage long-lived local-only research.

