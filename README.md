# AI Registry — GitLab (Inferred)

> **Inferred vendor repository.** This repo is maintained by the [AI Registry](https://github.com/eclipsefdn-ai-registry/ai-registry-core) project, not by GitLab. It pre-seeds the registry with Agent Skills published by GitLab at [gitlab.com/gitlab-org/ai/skills](https://gitlab.com/gitlab-org/ai/skills), plus an approval for GitLab's own official MCP server, which is already listed in the official MCP registry.
>
> _This entry is based solely on information published through GitLab's official public channels. GitLab has not endorsed, approved or validated this listing, and is not necessarily participating in the AI Registry._

## What this repo contains

**Agent Skills**

- All skills under `skills/*` in [gitlab-org/ai/skills](https://gitlab.com/gitlab-org/ai/skills) — a repo owned directly by GitLab's own `gitlab-org` group on GitLab.com (the same group that owns the main `gitlab-org/gitlab` product repo), MIT-licensed, and actively maintained (37 stars, 14 forks at the time of writing). It bundles first-party skills for `glab`-based GitLab workflows (MR review, MR descriptions, pipeline babysitting, GLQL queries), plus general agent-tooling skills (commit messages, handoff, skill authoring). At least one skill (`mr-review`) carries an explicit `metadata.author: gitlab` in its `SKILL.md` frontmatter; the rest rely on direct org ownership of the whole repo as their first-party signal. The approval uses a `skills/*` glob so newly published skills are picked up automatically on the next registry consolidation.

**MCP Server**

- **GitLab MCP Server** (`com.gitlab/mcp`) — GitLab's own MCP server, already listed as `status: active` in the official [MCP registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=gitlab) under the name `com.gitlab/mcp`, with its `repository` field pointing to `gitlab.com/gitlab-org/gitlab` (source: `gitlab`). Because it's registry-listed, this approval only needs `serverId` and `date` — name, description, and version are enriched automatically from the registry during consolidation. It also supplies a generic `config` (`type: http`, `url: https://gitlab.com/api/v4/mcp`) taken from GitLab's own [MCP server docs](https://docs.gitlab.com/user/model_context_protocol/mcp_server/), which describe this as the manual/generic client setup; authentication happens via OAuth 2.0 Dynamic Client Registration, so no client ID/secret is needed in the config. Requires GitLab Premium or Ultimate.

**Agent Plugins**

No Agent Plugin approval is included: no [agent-plugins.org](https://agent-plugins.org)-conformant plugin was found published by GitLab. The `gitlab-org/ai/skills` repo does ship `.claude-plugin/plugins/*/plugin.json` manifests, but these are Claude Code's own plugin-marketplace format, not agent-plugins.org's — each plugin's manifest points back at a shared `skills/` folder at the repo root (e.g. via a `"skills": "./"` field) rather than nesting its own `skills/<name>/SKILL.md` folders alongside `plugin.json`, which is what the agent-plugins.org spec (and this registry's consolidation logic) expects.

**A2A Agents**

No A2A agent approval is included: no published `agent_card.json` conforming to the Agent2Agent protocol was found for a GitLab-maintained agent.

## Documentation

See the [Vendor Guide](https://github.com/eclipsefdn-ai-registry/ai-registry-core#vendor-guide) in the central repository for how vendor repos work, how to add approvals, and how validation runs.
