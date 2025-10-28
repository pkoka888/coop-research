Claude Code Plugins & MCP – Best Practices

Plugins
- Keep plugins project-local with `--plugin-dir` where possible.
- Version and pin plugin repos; prefer release tags.

MCP (Model Context Protocol)
- Use `--mcp-config` with JSON files; use `--strict-mcp-config` to avoid loading unexpected servers.
- Define servers for filesystem, browser-tools, etc., with minimal permissions.

Security & Permissions
- Prefer default permission mode; only use `--dangerously-skip-permissions` in isolated sandboxes.

Structure
- Keep MCP configs under `.mcp/servers/*.json` or `.yaml`, document each server’s purpose and scope.

