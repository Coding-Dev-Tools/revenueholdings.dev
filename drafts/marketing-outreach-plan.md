# External Distribution & Marketing Outreach Plan
**Issue: COM-138 — Drive awareness to 13 zero-star repos**
**Date: 2026-05-15**

---

## Current State
- 13 public repos, all 0 stars, 0 forks
- Repos under `Coding-Dev-Tools` GitHub org
- Landing page: revenueholdings.dev (13 pages)
- Blog: 5 articles posted
- Zero external traffic / distribution

---

## 1. Product Hunt Launch Plan — click-to-mcp

**Why click-to-mcp first:** 66M+ FastMCP downloads prove massive MCP market demand. Zero "Click-to-MCP" competitors exist. This is a wide-open niche that bridges Python's most popular CLI framework (Click/typer) into the MCP ecosystem.

### Pre-Launch (T-7 days)
- [ ] Create maker profile on Product Hunt
- [ ] Prepare assets: logo (256x256), gallery images (1270x760), tagline
- [ ] Record 60-sec demo video: `pip install click-to-mcp` → `click-to-mcp convert mycli` → instant MCP server
- [ ] Write maker comment with technical deep-dive
- [ ] Line up 5-10 hunter/upvoter supporters (indie dev communities)

### Launch Day
- [ ] Submit between 12:01 AM PST (maximize 24h window)
- [ ] Tagline: **"Turn any Click/typer CLI into an MCP server — one command"**
- [ ] Categories: Developer Tools, Open Source, AI
- [ ] First comment: origin story + technical architecture diagram
- [ ] Cross-post to Twitter/X, Reddit r/Python, r/MCP, r/LocalLLaMA
- [ ] Share in Discord: FastMCP server, Python Discord, MCP community

### Tagline options:
1. "Turn any Click/typer CLI into an MCP server — one command"
2. "66M FastMCP downloads. Zero Click-to-MCP wrappers. Until now."
3. "Your Python CLI already works. Now it talks to AI agents too."

### Gallery images (5):
1. Hero: CLI → MCP server in 3 steps
2. Before/After: Regular Click app vs MCP-enabled
3. Architecture: Click CLI → click-to-mcp → MCP Protocol → LLM
4. Compatibility matrix: Click, typer, argparse wrappers
5. Example: Claude Desktop using a Click tool via MCP

---

## 2. Show HN Draft — SchemaForge v1.7.0

```
Title: Show HN: SchemaForge – Convert between 11 ORM schema formats (SQL, Prisma, Drizzle, Django, etc.)

Body:
I built SchemaForge because every time I switched projects, I spent hours manually converting between ORM schema definitions — SQL DDL to Prisma, Prisma to Drizzle, Django models to SQLAlchemy... 

SchemaForge is a CLI + VS Code extension that does bidirectional conversion between 11 schema formats:
- SQL DDL, Prisma, Drizzle, TypeORM, Django, SQLAlchemy, Alembic migrations, JSON Schema, GraphQL SDL, EF Core (C#), Scala case classes

That's 110 direction pairs, all with zero-loss roundtripping (preserves constraints, indexes, relations, defaults).

Key features:
- 270 tests covering edge cases across all format pairs
- VS Code extension with live preview (Ctrl+Alt+S), format detection (Ctrl+Alt+D), and two-file diff
- Custom .schemaforge editor in VS Code
- Streaming for large schemas

Install: pip install schemaforge
VS Code: Search "SchemaForge" in extensions

v1.7.0 adds the VS Code companion, custom editor, and format detection.

Built with Python + Click. Would love feedback on what format pairs are most useful or what's missing.
```

---

## 3. Reddit Post Drafts

### r/Python — click-to-mcp
```
Title: I made a tool that auto-wraps any Click/typer CLI as an MCP server

With the MCP (Model Context Protocol) ecosystem exploding (66M+ FastMCP downloads), I realized there was no easy way to bridge existing Python CLIs into the MCP world. 

click-to-mcp takes any Click or typer CLI and generates a fully compliant MCP server — one command:

    pip install click-to-mcp
    click-to-mcp convert your_cli_app

Now your CLI tools can be called by Claude, GPT, or any MCP-compatible agent.

Works with: Click apps, typer apps, and even wraps argparse CLIs through Click's compatibility layer.

GitHub: https://github.com/Coding-Dev-Tools/click-to-mcp
Docs: https://revenueholdings.dev/quickstart.html

Would love feedback — what CLIs would you wrap?
```

### r/webdev — SchemaForge
```
Title: Built a tool to convert between Prisma, Drizzle, TypeORM, SQL, and 7 more ORM formats

Tired of manually rewriting schema definitions when switching between projects or ORMs. Built SchemaForge — bidirectional converter between 11 schema formats (110 direction pairs).

    pip install schemaforge
    schemaforge convert input.prisma --to drizzle

Also has a VS Code extension with live preview and format detection.

Supports: SQL DDL, Prisma, Drizzle, TypeORM, Django, SQLAlchemy, Alembic, JSON Schema, GraphQL SDL, EF Core, Scala case classes.

GitHub: https://github.com/Coding-Dev-Tools/schemaforge
```

### r/devops — api-contract-guardian
```
Title: CLI tool to detect breaking API changes before they hit production

api-contract-guardian monitors OpenAPI schema diffs between git branches, detects breaking changes, and can block CI pipelines on contract violations.

    pip install api-contract-guardian
    api-contract-guardian check main..feature

It also generates migration guides for the breaking changes it finds. Useful for teams with microservices where API contract violations cause production incidents.

Also has MCP integration — your AI agents can check API contracts too.

GitHub: https://github.com/Coding-Dev-Tools/api-contract-guardian
```

### r/LocalLLaMA — click-to-mcp + MCP suite
```
Title: Open-source tools to expose your Python CLIs as MCP servers

The MCP ecosystem needs more tool servers. I built click-to-mcp to auto-wrap any Click/typer CLI as a compliant MCP server:

    pip install click-to-mcp
    click-to-mcp convert your_cli

This lets any MCP-compatible client (Claude Desktop, Continue, etc.) call your CLI tools directly.

Our org also has 2 other MCP-enabled tools:
- api-contract-guardian: AI-powered API contract testing
- apighost: Mock servers from OpenAPI specs with VCR recording

All open-source, all pip-installable. Would love to hear what tools people want exposed via MCP.
```

---

## 4. dev.to / Medium Article Drafts

### Article 1: "Turn Any Python CLI into an MCP Server in 5 Minutes" (click-to-mcp)

```markdown
# Turn Any Python CLI into an MCP Server in 5 Minutes

The Model Context Protocol (MCP) is the new standard for connecting AI agents to external tools. With 66M+ FastMCP downloads, the ecosystem is exploding — but most Python CLI tools can't participate because they weren't built for MCP.

That's where click-to-mcp comes in.

## What it does
click-to-mcp auto-wraps any Click or typer CLI as a fully compliant MCP server. One command, zero code changes.

## Quick start
    pip install click-to-mcp
    click-to-mcp convert my_cli_app
    click-to-mcp serve  # Starts the MCP server

## Why this matters
- **100K+ Click/typer CLIs on PyPI** — none of them talk to AI agents
- **66M+ FastMCP downloads** — massive demand for MCP tool servers
- **Zero competitors** — no other Click-to-MCP wrapper exists

## How it works
[architecture diagram: Click CLI → introspection → MCP tool definitions → MCP server]

## Real example: Wrap the AWS CLI
    click-to-mcp convert awscli
Now Claude can directly invoke AWS commands through MCP.

## Try it
- GitHub: https://github.com/Coding-Dev-Tools/click-to-mcp
- Docs: https://revenueholdings.dev/quickstart.html
```

### Article 2: "Never Rewrite an ORM Schema Again: 11-Format Bidirectional Conversion" (SchemaForge)

```markdown
# Never Rewrite an ORM Schema Again: 11-Format Bidirectional Conversion

Every developer who switches projects has faced this: your last project used Prisma, this one uses Drizzle, and the schema definitions are completely incompatible. Manual conversion takes hours and loses constraints.

## SchemaForge solves this
Bidirectional conversion between 11 schema formats — SQL DDL, Prisma, Drizzle, TypeORM, Django, SQLAlchemy, Alembic, JSON Schema, GraphQL SDL, EF Core, and Scala case classes. 110 direction pairs, all zero-loss.

## Quick start
    pip install schemaforge
    schemaforge convert schema.prisma --to drizzle

## VS Code Extension
Live preview, quick convert (Ctrl+Alt+S), format detection (Ctrl+Alt+D), and two-file diff — all inside VS Code.

## 270 tests
Every format pair is tested with real-world schemas covering constraints, indexes, relations, and defaults.

## Try it
- GitHub: https://github.com/Coding-Dev-Tools/schemaforge
- VS Code: Search "SchemaForge" in extensions
```

---

## 5. GitHub Topic Tags — Improvements

Current topics are good but missing high-traffic search terms. Recommended additions:

| Repo | Current Topics | Add These |
|------|---------------|-----------|
| click-to-mcp | cli-wrapper, developer-tools, mcp, model-context-protocol, ai-tools, cli, click, python, typer | **mcp-server, fastmcp, ai-agent, llm-tools, mcp-cli** |
| schemaforge | cli, developer-tools, drizzle, format-converter, orm, prisma, python, schema-converter, sqlalchemy, typescript | **mcp, vsce, schema-migration, database-tools, migration** |
| api-contract-guardian | api-contract-testing, breaking-changes, ci-cd, cli, developer-tools, openapi, mcp, model-context-protocol | **schema-diff, api-versioning, contract-testing, rest-api** |
| deadcode | cli, code-cleanup, dead-code, developer-tools, linter, nextjs, python, react, static-analysis | **tree-shaking, unused-code, javascript, typescript, react-cleanup** |
| apighost | api-mocking, cli, developer-tools, mock-server, openapi, python, testing, mcp | **vcr, api-testing, http-mock, fastapi** |
| configdrift | cli, configuration-management, developer-tools, devops-tools, drift-detection, env, yaml | **terraform, ansible, devsecops, infrastructure-as-code, toml** |
| deploydiff | cli, cloudformation, cost-estimation, developer-tools, devops-tools, infrastructure, terraform | **pulumi, iac, infracost, infrastructure-as-code, plan-diff** |
| json2sql | cli, data-migration, database-tools, developer-tools, json, sql | **etl, data-pipeline, postgresql, mysql, sqlite** |
| envault | cli, developer-tools, devops, dotenv, env-variables, python, secrets-management | **vault, aws-secrets-manager, key-rotation, dotenv-sync** |
| datamorph | cli, csv, data-converter, developer-tools, etl, json, parquet, python, yaml | **avro, protobuf, data-engineering, streaming** |
| apiauth | api-keys, authentication, cli, developer-tools, jwt, python, security | **oauth, api-security, key-management, token-rotation** |
| vscode-schemaforge | developer-tools, orm, prisma, schema-converter, sql, vscode-extension | **vscode, drizzle, typeorm, django, sqlalchemy** |

---

## 6. Star-Boosting — Self-Star

All org members should star every public repo. This takes 2 minutes and moves repos from 0→1+ which eliminates the "0 stars = abandoned" perception barrier.

Repos to star (13):
1. https://github.com/Coding-Dev-Tools/click-to-mcp
2. https://github.com/Coding-Dev-Tools/schemaforge
3. https://github.com/Coding-Dev-Tools/api-contract-guardian
4. https://github.com/Coding-Dev-Tools/deadcode
5. https://github.com/Coding-Dev-Tools/apighost
6. https://github.com/Coding-Dev-Tools/configdrift
7. https://github.com/Coding-Dev-Tools/deploydiff
8. https://github.com/Coding-Dev-Tools/json2sql
9. https://github.com/Coding-Dev-Tools/envault
10. https://github.com/Coding-Dev-Tools/datamorph
11. https://github.com/Coding-Dev-Tools/apiauth
12. https://github.com/Coding-Dev-Tools/vscode-schemaforge
13. https://github.com/Coding-Dev-Tools/revenueholdings.dev

---

## 7. Execution Priority

1. **IMMEDIATE** — Self-star all repos (2 min, removes "0 stars" stigma)
2. **IMMEDIATE** — Add missing GitHub topics (5 min, improves discoverability)
3. **TODAY** — Post Show HN for SchemaForge
4. **TODAY** — Post Reddit r/Python for click-to-mcp
5. **THIS WEEK** — Publish dev.to article for click-to-mcp
6. **THIS WEEK** — Reddit r/webdev, r/devops, r/LocalLLaMA
7. **NEXT WEEK** — Product Hunt launch for click-to-mcp (needs prep)
8. **NEXT WEEK** — dev.to article for SchemaForge
