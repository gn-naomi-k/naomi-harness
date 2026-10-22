# Naomi pi harness

Declarative configuration for Naomi's pi coding-agent setup.

## Included

- pi defaults, extensions, and skill path
- model allowlist
- npm extension dependency manifest and lockfile
- MCP server template with credentials replaced by placeholders

## Restore

```sh
mkdir -p ~/.pi/agent/npm
cp pi/agent/settings.json ~/.pi/agent/settings.json
cp pi/agent/model-filter.json ~/.pi/agent/model-filter.json
cp pi/agent/mcp.json.example ~/.pi/agent/mcp.json
# Edit ~/.pi/agent/mcp.json and add credentials locally.
cp pi/agent/npm/package.json ~/.pi/agent/npm/package.json
cp pi/agent/npm/package-lock.json ~/.pi/agent/npm/package-lock.json
(cd ~/.pi/agent/npm && npm ci)
```

The configured `~/.claude/skills` path is intentionally left as a local dependency.

## Security

Credentials, auth state, sessions, caches, model catalogs, crash logs, and installed dependencies are not tracked. Do not commit a populated `mcp.json`; use the example as a template only.
