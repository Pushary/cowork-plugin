# Pushary for Claude Cowork

Phone notifications and human-in-the-loop for [Claude Cowork](https://pushary.com/claude-cowork-notifications). Cowork pings your phone when a task finishes and asks you questions you answer from your lock screen, so long tasks never sit frozen waiting for you.

- **Notify when done.** Cowork calls `send_notification` with a summary when a task completes or fails.
- **Ask before risky steps.** Cowork calls `ask_user` before deleting, overwriting, spending, or sending anything external. You tap yes or no on your phone.
- **One inbox for every agent.** The same Pushary account covers Claude Code, Codex, Cursor, and Hermes, with an audit trail of every question and answer.

## Install

Follow [SETUP.md](./SETUP.md). Short version: paste your Pushary connector link into Claude under Settings, Connectors, then enable Pushary inside your Cowork session under Customize, Connectors.

## What's in this plugin

- `skills/pushary-cowork/SKILL.md`: teaches Claude when to notify you and how to ask questions through the connector, including the async pattern for long unattended sessions.
- `SETUP.md`: the full connector setup walkthrough.

## Honest scope

Cowork exposes no hooks, so this integration is cooperative: Claude decides when to call the tools, guided by the skill. It does not physically block an action until you approve. Enforced approvals are available for Claude Code, Codex, Gemini CLI, Cursor, and Hermes via [`@pushary/agent-hooks`](https://pushary.com/docs).

## Links

- [Docs: Claude.ai, Claude Desktop, and Cowork](https://pushary.com/docs/agents/guides/claude-desktop)
- [Pushary dashboard](https://pushary.com/dashboard/agent/settings)
- Support: aadil@pushary.com
