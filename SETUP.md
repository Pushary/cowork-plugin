# Set up Pushary for Claude Cowork

Pushary sends Cowork's questions and completion notices to your phone as push notifications. You answer from the lock screen and the session keeps going. Setup is one pasted link.

## 1. Get your connector link

1. Sign up at [pushary.com](https://pushary.com/sign-up) (agent plans start with a 3-day trial at $9.99 per month)
2. Open [Settings, Connections](https://pushary.com/dashboard/agent/settings)
3. In the **Claude (claude.ai, Desktop, and Cowork)** section, click **Get connector link** and copy it

The link is a dedicated, revocable key scoped to notifications and questions only. Treat it like a password.

## 2. Add it in Claude

1. In Claude, open **Settings**, then **Connectors**, then **Add custom connector**
2. Leave the OAuth fields empty and paste your link into the **Remote MCP server URL** field
3. Name it `Pushary` and click **Add**

Connectors are account level, so the same connector is available inside Cowork on desktop, web, and mobile. In a Cowork session, open **Customize**, then **Connectors**, and turn on Pushary.

## 3. Make Cowork reach out on its own

This plugin's skill teaches Claude when to notify you and how to ask. For belt and braces, also paste the standing instructions block from your [Pushary dashboard](https://pushary.com/dashboard/agent/settings) into Claude **Settings**, then **Cowork**, so every session asks before risky steps and pings you when tasks finish.

## 4. Get your phone ready

Install the Pushary app ([iPhone](https://pushary.com/download) or [Android](https://pushary.com/download)), or enable web push in any browser from the dashboard. Questions arrive as push notifications you answer from the lock screen.

## What this is, honestly

Cowork has no hooks, so this is a cooperative integration: Claude decides when to call the tools, guided by the skill and your standing instructions. Nothing physically blocks Cowork until you answer. If you want enforced approvals that stop a command until you say yes, use Pushary with Claude Code, Codex, Gemini CLI, Cursor, or Hermes: `npx @pushary/agent-hooks setup`.

## Example prompts

```
Draft the investor update from the Q2 folder. Ask me on my phone before
sending anything, and ping me when the draft is ready.
```

```
Reconcile these two spreadsheets. If anything looks off, ask me instead of
guessing. Notify me when you are done.
```
