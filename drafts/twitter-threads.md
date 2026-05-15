# Twitter/X Thread Drafts — Revenue Holdings

---

## Thread 1: click-to-mcp (AI/ML audience)

**Tweet 1** 🧵
You know what's wild? Every Click/Typer CLI already IS an MCP server, it just doesn't know it yet.

I built a tool that makes it realize its true potential.

👇

**Tweet 2**
Meet click-to-mcp — it auto-wraps any Python CLI as an MCP server.

`pip install click-to-mcp`
`click-to-mcp serve your-cli`

That's it. Your CLI is now available to Claude Code, Cursor, and any MCP client.

**Tweet 3**
How it works:
• Click commands → MCP tools
• Arguments → required inputs
• Options → optional params  
• Choices → enums
• Nested groups → prefixed tools

No annotations. No decorator soup. Just introspection at runtime.

**Tweet 4**
Why I built it:
MCP is the hottest protocol in AI dev tools (66M+ FastMCP downloads). But converting a CLI to MCP meant rewriting it. I wanted every existing CLI to be instantly MCP-compatible.

**Tweet 5**
Real example:
```json
// .claude/settings.json
{
  "mcpServers": {
    "api-contract-guardian": {
      "command": "click-to-mcp",
      "args": ["serve", "api-contract-guardian"]
    }
  }
}
```

Now Claude Code validates API contracts without leaving the chat.

**Tweet 6**
v0.4.0 just shipped with Streamable HTTP transport. Works great for web-based MCP clients too.

Or try the demo: `click-to-mcp demo`

GitHub → https://github.com/Coding-Dev-Tools/click-to-mcp

---

## Thread 2: DeadCode (frontend/React audience)

**Tweet 1** 🧵
Your React/Next.js project has dead code. Lots of it. Unused components, dead API routes, orphaned CSS that shipped to production.

I built a CLI that finds every piece of it.

🧵 ↓

**Tweet 2**
DeadCode scans your codebase and reports:
• Unused exports & imports
• Dead API routes
• Orphaned CSS classes
• Unreferenced components

TypeScript, JSX, TSX — all supported.

**Tweet 3**
`pip install deadcode`
`deadcode scan ./src`

Output is actionable — tells you exactly what to remove and which files to edit.

**Tweet 4**
It's not just a linter. DeadCode does tree-shaking-aware analysis. It can tell the difference between "unused export" and "export used in a barrel file, then never imported".

**Tweet 5**
Real impact: I ran it on a 6-month-old Next.js project. Found:
- 23 unused components  
- 4 dead API routes from an abandoned feature
- 312 lines of orphaned CSS
- 15 unnecessary imports

Cleanup took 20 minutes. Bundle size dropped 18%.

**Tweet 6**
Free. Open source. Works today.

GitHub → https://github.com/Coding-Dev-Tools/deadcode

---

## Thread 3: SchemaForge (backend/DB audience)

**Tweet 1** 🧵
I spent 6 months building a tool I wish existed 3 years ago:

A bidirectional schema converter that roundtrips between 11 formats without data loss.

SQL ↔ Prisma ↔ Drizzle ↔ TypeORM ↔ Django ↔ SQLAlchemy — any pair, both ways.

🧵 ↓

**Tweet 2**
The problem with existing schema converters:
❌ One-direction only (SQL → Prisma, but not back)
❌ Lose CHECK constraints, custom types, views
❌ Require manual cleanup after conversion

SchemaForge does none of that.

**Tweet 3**
11 supported formats:
• SQL DDL (MySQL, PG, SQLite)
• Prisma schema
• Drizzle ORM
• TypeORM entities
• Django models
• SQLAlchemy models
• JSON Schema / OpenAPI
• Knex.js, Sequelize, Mongoose
• Zod schemas (experimental)

**Tweet 4**
The roundtrip test:
SQL → Prisma → SQL = identical schema.
CHECK constraints. Composite keys. Indexes. Custom types.
All preserved.

Also available as a VS Code extension with live preview.

**Tweet 5**
Use cases:
• Migrating from Prisma to Drizzle
• Generating SQL migrations from TypeORM
• Converting a Django project to SQLAlchemy
• Sharing schema between backend (SQL) and API docs (OpenAPI)

**Tweet 6**
CLI one-liner:
`schemaforge convert schema.prisma --to sql`

VS Code extension → https://github.com/Coding-Dev-Tools/vscode-schemaforge
GitHub → https://github.com/Coding-Dev-Tools/schemaforge

---

## Thread 4: api-contract-guardian (API/DevOps audience)

**Tweet 1** 🧵
You know that feeling when a teammate merges an OpenAPI change that breaks your integration?

I built a CLI that catches breaking API changes before they hit production.

And then blocks the CI pipeline. Automatically.

🧵 ↓

**Tweet 2**
api-contract-guardian (acg for short):
`acg diff --base openapi.yaml --head openapi.yaml`
`acg validate openapi.yaml`

Detects: removed endpoints, changed response schemas, required → optional fields, altered types.

**Tweet 3**
It generates a migration guide for every breaking change:
```
⚠️ BREAKING: DELETE /users/{id} was removed
ℹ️ Migration: Migrate to POST /users/{id}/deactivate
```

**Tweet 4**
CI integration:
```yaml
- name: Check API contract
  run: acg diff --base main:openapi.yaml --head HEAD:openapi.yaml
```

Fails the build on contract violations. Your API contract stays clean.

**Tweet 5**
Bonus: Works with click-to-mcp as an MCP server for Claude Code.

"Validate our API contract" → Claude calls acg automatically.

**Tweet 6**
GitHub → https://github.com/Coding-Dev-Tools/api-contract-guardian

Part of the Revenue Holdings CLI suite → https://coding-dev-tools.github.io/revenueholdings.dev/
