# Codex and Claude Code setup notes

Verified against the linked official pages on 2026-11-01. Recheck version-sensitive behavior before changing setup. This guide describes capabilities; it does not install tools or change permissions.

## Shared project instructions and context

Keep project facts and commands in a concise `AGENTS.md`. A Claude `CLAUDE.md` with an actual `@AGENTS.md` import shares those rules. Select local guides and workflows; do not import the whole library. In a folder without a recognized project root, Codex checks its current directory for project instructions, so launch it in the intended folder. [Codex instruction discovery](https://learn.chatgpt.com/docs/agent-configuration/agents-md), [Claude memory](https://code.claude.com/docs/en/memory).

Codex discovers project skills under `.agents/skills`; Claude Code uses `.claude/skills`. Both support loading skills when relevant. Keep portable workflow bodies small, give descriptions precise triggers, and put conditional details in references. Keep host-specific metadata separate. Discovery still has overhead; copying every workflow into every project defeats selection. [Codex skills](https://learn.chatgpt.com/docs/build-skills), [Claude skills](https://code.claude.com/docs/en/skills).

## Claude-specific capabilities

- `/init` drafts starting instructions from a codebase. Inspect its output, remove obvious/redundant material, and merge useful facts into existing project instructions.
- Project subagents live in `.claude/agents/`. Current `/agents` behavior differs from older wizard-based versions; ask Claude to create a definition or edit the file. A subagent's `skills:` list preloads full skill bodies, so include only what its job needs. A subagent's `tools` field and a skill's `allowed-tools` field have different meanings.
- A skill's `allowed-tools` preapproves listed calls; it does not restrict all other tools. Claude also supports skill `model` and invocation controls. Review these fields before invocation and do not assume another host enforces them.

Use the current [best practices](https://code.claude.com/docs/en/best-practices), [subagent](https://code.claude.com/docs/en/sub-agents), and [skill](https://code.claude.com/docs/en/skills) references for exact syntax.

Claude Code already manages prompt caching and compaction. Caching reduces repeated processing, not context size. Preserve goals, decisions, verification evidence, authority, and the next task in a short durable handoff at useful boundaries. It also documents an experimental advisor tool; check account/model/provider support and cost before choosing it. Avoid building another cache or advisor layer without a demonstrated need. [Prompt caching](https://code.claude.com/docs/en/prompt-caching), [advisor](https://code.claude.com/docs/en/advisor).

## MCP and documentation tools

Use `/mcp` inside Claude Code or `claude mcp list` to inspect configured servers. Prefer an available authoritative documentation tool for version-sensitive library questions. [Context7](https://github.com/upstash/context7) is an optional candidate, not a prerequisite or an automatically enabled service. Match documentation to the installed dependency version and keep private code, identifiers, and secrets out of queries.

Review a server's executable or remote endpoint, data payloads, credential scope, and tool effects before connecting it. Current Claude MCP tool search defers definitions, so older fixed tool-count/context-loss claims should not become universal rules. Select tools by task and actual context measurements. [Claude MCP documentation](https://code.claude.com/docs/en/mcp).
