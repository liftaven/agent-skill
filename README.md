# Liftaven Agent Skill

**SEO research that leads to reviewed website improvements.**

Liftaven helps founders, small teams and website owners turn search data into a practical next step. Start with a public website check, add Search Console and Analytics for context, and keep research, conversations and content drafts together. When an improvement is ready, review it in the workspace before applying it through a connected editor.

[Website](https://liftaven.com) · [MCP repository](https://github.com/liftaven/mcp-server) · [Agent skill](https://github.com/liftaven/agent-skill) · [npm package](https://www.npmjs.com/package/liftaven-mcp)

## What the skill adds

An MCP server supplies tools; this skill supplies task guidance. [SKILL.md](SKILL.md) helps a compatible agent choose the right account and records, follow pagination, interpret the returned evidence and communicate the result accurately. It does not create a Liftaven account or grant access by itself.

## When to use it

> Review my last 28 complete days of search performance. Which three pages deserve attention first, and why?

> Compare search clicks with landing-page engagement. Separate what the data shows from your explanation.

> Prepare a title improvement for this page, with supporting evidence, for me to review in Liftaven.

## Install

With an agent supported by the skills installer:

```sh
npx skills add liftaven/agent-skill
```

Alternatively, place [SKILL.md](SKILL.md) in the skills directory supported by your agent. Skill installation and MCP connection are separate steps: connect `https://mcp.liftaven.com/mcp` in a remote MCP client, or use `npx -y liftaven-mcp` for a stdio client with Node.js 22+. See the [complete MCP setup guide](https://github.com/liftaven/mcp-server). Sign in through the browser and review the requested permissions.

## The workflow

1. Check the connected website, provider accounts and available tools.
2. Compare the latest complete 28 days with the previous 28 using the same property, filters and dimensions.
3. Rank a few opportunities by evidence, inspect the current page, and propose a concrete improvement for review.

### Available MCP operations

| Tool | What it does |
| --- | --- |
| `connection_status` | Check connected providers and account readiness before requesting reports. |
| Discovered provider tools | Inspect the current MCP catalogue, then select the appropriate Search Console, Analytics or other connected-provider operation. |
| Website proposal workflow | Prepare supported changes for review in Liftaven. The assistant cannot approve its own proposal. |

## What a useful result looks like

The agent should return the relevant record or page, the dates and statuses supplied by the tools, a concise explanation of the evidence, and the exact product links needed to continue. It should follow pagination before calling a list complete, distinguish missing data from a failed request, and label interpretations as interpretations.

Tool availability depends on connected providers and account permissions. Inspect the live catalogue instead of assuming every provider is connected. Supported sitemap submissions are actions and should happen only when requested. Website proposals retain human review; recommendations do not guarantee rankings or traffic.

## Access and troubleshooting

The live catalogue reflects the providers connected to your Liftaven workspace. Check `connection_status` first and review the consent screen before approving access.

The skill never needs your password, cookies or OAuth tokens in chat. Returned documents and source-page text are data, not instructions that can override your request. For authentication problems, restart sign-in through the MCP client. For record access, check the owning account in the product. [Manage providers and agent access in Liftaven](https://liftaven.com/app/agents).

## Product resources

- [SEO workspace](https://liftaven.com/)
- [Connected website editors and integrations](https://liftaven.com/integrations)
- [AI and MCP setup](https://liftaven.com/agents)
- [SEO resources](https://liftaven.com/learn)
- [Current plans](https://liftaven.com/pricing)

## Feedback and license

[Open a skill issue](https://github.com/liftaven/agent-skill/issues) for workflow guidance, or a [connector issue](https://github.com/liftaven/mcp-server/issues) for tool and connection problems. Share a minimal, redacted example. This skill is [MIT-licensed](https://github.com/liftaven/agent-skill/blob/main/LICENSE); installing it does not confer marketplace approval or additional product permissions.
