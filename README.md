# Pushary for Claude Cowork

Phone notifications and human-in-the-loop for [Claude Cowork](https://pushary.com/claude-cowork-notifications). Cowork pings your phone when a task finishes and asks you questions you answer from your lock screen, so long tasks never sit frozen waiting for you.

- **Notify when done.** Cowork calls `send_notification` with a summary when a task completes or fails.
- **Ask before risky steps.** Cowork calls `ask_user` before deleting, overwriting, spending, or sending anything external. You tap yes or no on your phone.
- **One inbox for every agent.** The same Pushary account covers Claude Code, Codex, Cursor, and Hermes, with an audit trail of every question and answer.

## Install

Follow [SETUP.md](./SETUP.md). Three steps, and none of them is optional:

1. Paste your Pushary connector link into Claude under **Settings**, **Connectors**.
2. Enable Pushary inside your Cowork session under **Customize**, **Connectors**.
3. Paste the standing instructions block into Claude under **Settings**, **Cowork**. Cowork does not read `CLAUDE.md`, `AGENTS.md`, or any repo memory file, so this is the only place a proactive-use directive reaches it.

The skill in this repo is also published to skills.sh:

```bash
npx skills add Pushary/pushary-skill
```

## What's in this plugin

- `skills/pushary-cowork/SKILL.md`: teaches Claude when to notify you and how to ask questions through the connector, including the async pattern for long unattended sessions.
- `SETUP.md`: the full connector setup walkthrough.

## Honest scope

Cowork exposes no hooks, so this integration is cooperative: Claude decides when to call the tools, guided by the skill and your standing instructions. It does not physically block an action until you approve. Enforced approvals are available for Claude Code, Codex, Gemini CLI, Cursor, and Hermes via [`@pushary/agent-hooks`](https://pushary.com/docs).

The connector is also outbound only. Cowork can reach your phone; your phone cannot push work into a Cowork session. So you can answer anything Cowork asks, but you cannot reply to a finished task or start a new one from the app unless Cowork left a question open before it stopped. The standing instructions tell it to do exactly that when a reply is likely.

## Links

- [Docs: Claude.ai, Claude Desktop, and Cowork](https://pushary.com/docs/agents/guides/claude-desktop)
- [Pushary dashboard](https://pushary.com/dashboard/agent/settings)
- Support: aadil@pushary.com
