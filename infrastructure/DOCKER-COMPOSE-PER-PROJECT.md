Docker Compose – Per-Project Patterns

Goals
- Unique container names and ports per project; avoid cross-project clashes.

Patterns
- Use `.env` with `PROJECT_SLUG`, `REDIS_PORT`, `QDRANT_HTTP_PORT`, `QDRANT_GRPC_PORT`.
- In compose, set `container_name: ${PROJECT_SLUG}-service` and port maps `${PORT}:...`.

Automation
- Generate env via script (we provide `scripts/docker-compose-env.ps1`) that picks free ports.
- Guard start when Docker isn’t running; verify health via dedicated script.

