# Pushary for Claude Cowork

Connect Cowork’s questions and task updates to your phone and Mac notch.

## Setup

Install this plugin in Claude to load the Cowork skill and the bundled remote MCP connector. Sign in with the same Pushary account used by your phone and Mac app, then enable Pushary in the task. If the connector is not added by your Claude version, add `https://pushary.com/api/mcp/mcp` under **Customize > Connectors > Add custom connector**. Leave OAuth Client ID and Secret empty.

For the manual path, run `npx @pushary/agent-hooks@latest cowork` or follow [SETUP.md](SETUP.md). No local CLI installation is required for the connector. The CLI command prints setup instructions; it does not configure your Claude account automatically.

Use the bundled skill or add standing instructions in **Settings > Cowork** to guide proactive use. Ask Cowork a harmless Pushary test question, answer from your phone or notch, and verify Cowork receives the answer. A successful notification alone does not verify answers.

## Included

- `.mcp.json`: the public OAuth connector, with no embedded key.
- `skills/pushary-cowork/SKILL.md`: when to ask, notify, and hand off unanswered questions.
- `SETUP.md`: account setup, verification, and recovery.

## Capabilities

This Pushary connector is cooperative: Claude chooses when to call its tools. It does not intercept native permission prompts, send new work into an ended turn, or launch Cowork tasks. It can wait for a question it asked and receive your answer on that existing request.

Cowork supports plugin hooks on supported versions. This package does not install or verify native permission hooks; that support must be tested separately for each surface and version. Cowork may run locally or in the cloud, while remote MCP connector calls come from Anthropic’s infrastructure.

[Full guide](https://pushary.com/docs/agents/guides/claude-desktop) · [Plugin support](https://support.claude.com/en/articles/13837440-use-plugins-in-claude)
