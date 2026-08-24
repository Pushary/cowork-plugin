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

This step is required, not optional. Cowork does not read `CLAUDE.md`, `AGENTS.md`, or any other repo memory file, so instructions you put there reach nothing and the session keeps going quietly as if you were watching it.

Copy the standing instructions block from your [Pushary dashboard](https://pushary.com/dashboard/agent/settings) and paste it into Claude under **Settings**, then **Cowork**. Every session then asks before risky steps, pings you when tasks finish, and leaves a question open when you are likely to want to reply.

## 4. Get your phone ready

Install the Pushary app ([iPhone](https://pushary.com/download) or [Android](https://pushary.com/download)), or enable web push in any browser from the dashboard. Questions arrive as push notifications you answer from the lock screen.

## What this is, honestly

Cowork has no hooks, so this is a cooperative integration: Claude decides when to call the tools, guided by the skill and your standing instructions. Nothing physically blocks Cowork until you answer. If you want enforced approvals that stop a command until you say yes, use Pushary with Claude Code, Codex, Gemini CLI, Cursor, or Hermes: `npx @pushary/agent-hooks setup`.

The connector is outbound only, too. Cowork reaches your phone; your phone cannot push work into a Cowork session, because there is no hook and nothing running on your machine to pick it up. In practice:

- You can answer any question Cowork asks, of any type, from the lock screen.
- You cannot reply to a finished task unless Cowork left a question open before it stopped. The standing instructions tell it to do that whenever a reply is likely.
- You cannot start a new Cowork task from the Pushary app. Messaging and launching agents from your phone are CLI features, because the CLI runs on your machine and can pick the work up. The app hides both controls on a Cowork session rather than queueing something that would never arrive.

## Example prompts

```
Draft the investor update from the Q2 folder. Ask me on my phone before
sending anything, and ping me when the draft is ready.
```

```
Reconcile these two spreadsheets. If anything looks off, ask me instead of
guessing. Notify me when you are done.
```
