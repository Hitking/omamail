# MCP — this project's knowledge server

`project.json` beside this file is the whole of what this repo carries. It describes the
project to an MCP "project knowledge server" so another repo — or an agent working in one —
can ask what this project is, what it exposes and how to call it, without cloning or
grepping it.

**The engine lives once, in content-studio**, and is shared by all seven projects:

```bash
node /home/masoud/Projects/content-studio/scripts/mcp/server.mjs --manifest <this folder>/project.json
```

That is exactly what the `.mcp.json` at this repo's root runs. Nothing to install — the
engine has no dependencies.

Try it, and check the route map it produces, with:

```bash
cd /home/masoud/Projects/content-studio
node scripts/mcp/probe.mjs         --manifest <this folder>/project.json project_overview
node scripts/mcp/verify-routes.mjs --manifest <this folder>/project.json
```

Full documentation, the tool list, how the per-framework route extractors work and the traps
that silently drop routes: [`content-studio/scripts/mcp/README.md`](../../../content-studio/scripts/mcp/README.md).
