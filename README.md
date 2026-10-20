# AI Registry — GitLab (Inferred)

> **Inferred vendor repository.** This repo is maintained by the [AI Registry](https://github.com/eclipsefdn-ai-registry/ai-registry-core) project, not by GitLab. It pre-seeds the registry with Agent Skills published by GitLab at [gitlab.com/gitlab-org/ai/skills](https://gitlab.com/gitlab-org/ai/skills), plus an approval for GitLab's own official MCP server, which is already listed in the official MCP registry.
>
> _This entry is based solely on information published through GitLab's official public channels. GitLab has not endorsed, approved or validated this listing, and is not necessarily participating in the AI Registry._

## What this repo contains

**Agent Skills**

- All skills under `skills/*` in [gitlab-org/ai/skills](https://gitlab.com/gitlab-org/ai/skills) — a repo owned directly by GitLab's own `gitlab-org` group on GitLab.com (the same group that owns the main `gitlab-org/gitlab` product repo), MIT-licensed, and actively maintained (37 stars, 14 forks at the time of writing). It bundles first-party skills for `glab`-based GitLab workflows (MR review, MR descriptions, pipeline babysitting, GLQL queries), plus general agent-tooling skills (commit messages, handoff, skill authoring). At least one skill (`mr-review`) carries an explicit `metadata.author: gitlab` in its `SKILL.md` frontmatter; the rest rely on direct org ownership of the whole repo as their first-party signal. The approval is an explicit list of 47 of the repo's 53 skills, not a `skills/*` glob: the catalog grew by 20 skills in one week (2026-10-09 to 2026-10-20), and a glob published them all unread. Six are left out as GitLab-internal: `gitlab-psql` and `gitlab-clickhouse` (GitLab's own GDK development databases), `postgresai` (GitLab's database-review tooling, maintained in `gitlab-org/gitlab`), `prep-start` (GitLab's internal Platform Readiness Enablement Process), `mr-label` (GitLab's internal MR label taxonomy, sourced from `internal.gitlab.com`), and `gitlab-rails-fix` (a workflow for fixing bugs in a `gitlab-org/gitlab` checkout). New skills are added after review rather than automatically.

**MCP Server**

- **GitLab MCP Server** (`com.gitlab/mcp`) — GitLab's own MCP server, already listed as `status: active` in the official [MCP registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=gitlab) under the name `com.gitlab/mcp`, with its `repository` field pointing to `gitlab.com/gitlab-org/gitlab` (source: `gitlab`). Because it's registry-listed, this approval only needs `serverId` and `date` — name, description, and version are enriched automatically from the registry during consolidation. It also supplies a generic `config` (`type: http`, `url: https://gitlab.com/api/v4/mcp`) taken from GitLab's own [MCP server docs](https://docs.gitlab.com/user/model_context_protocol/mcp_server/), which describe this as the manual/generic client setup; authentication happens via OAuth 2.0 Dynamic Client Registration, so no client ID/secret is needed in the config. Requires GitLab Premium or Ultimate.

**Agent Plugins**

Plugin approvals for three [agent-plugins.org](https://agent-plugins.org)-conformant plugins in [gitlab-org/ai/gitlab-duo-plugins](https://gitlab.com/gitlab-org/ai/gitlab-duo-plugins) (`create-issue`, `mr-review`, `stack-changes`). The `gitlab-org/ai/skills` repo also ships `.claude-plugin/plugins/*/plugin.json` manifests, but these are Claude Code's own plugin-marketplace format pointing back at the shared root `skills/` folder, not agent-plugins.org plugins, and are not approved.

**A2A Agents**

No A2A agent approval is included: no published `agent_card.json` conforming to the Agent2Agent protocol was found for a GitLab-maintained agent.

## Documentation

See the [Vendor Guide](https://github.com/eclipsefdn-ai-registry/ai-registry-core#vendor-guide) in the central repository for how vendor repos work, how to add approvals, and how validation runs.
