# design-agents

Six Claude Code slash commands that run a complete design sprint — from discovery to a merged PR — inside the codebase.

## Commands

| Command | What it does |
|---|---|
| `/rzp-design/discover` | Research synthesis: competitors, user pain, product audit, 3 design directions |
| `/rzp-design/conceptualize` | 6 lo-fi concepts generated and cut to a recommended hybrid |
| `/rzp-design/prototype` | Live Blade prototype built in-context on the real product |
| `/rzp-design/detail` | All states, edge cases, visual refinements, 5-pass quality review |
| `/rzp-design/refine` | Refinement pass incorporating designer feedback |
| `/rzp-design/deliver` | 6 quality gates run, PR opened |

## Setup

### Global (available in every project)

```bash
cp -r .claude/commands/rzp-design ~/.claude/commands/rzp-design
```

Restart Claude Code. The `/rzp-design/...` commands appear immediately.

### Project-level (available only in this repo)

Clone into your project root — the `.claude/commands/` folder is picked up automatically by Claude Code.

## Requirements

- [Claude Code](https://claude.ai/code)
- Playwright MCP configured (used by prototype, detail, refine, and deliver for in-browser navigation)

## Notes

These commands were built for a RazorpayX sprint (Blade design system, INR formatting, Indian FY periods). To adapt them for a different product, find and replace the product-specific references in each `.md` file.
