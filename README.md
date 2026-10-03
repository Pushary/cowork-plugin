# Pushary for Cowork

Get Cowork task updates and answer its questions from your phone or Mac notch. This is the existing Cowork plugin, with its repository, releases, and install identifiers preserved.

For Claude Chat or Claude Code, use [Pushary for Claude](https://github.com/Pushary/claude-plugin). Choose one Pushary plugin per app to avoid duplicate connectors. Both plugins use the same shared skill.

## Install

In Cowork, open **Customize > Plugins > Add > Add marketplace** and add `https://github.com/Pushary/cowork-plugin`. Install **Pushary for Cowork** from that marketplace. This GitHub installation does not require a directory listing.

The plugin identifier remains `pushary`, the marketplace identifier remains `pushary-claude`, and the skill identifier remains `pushary-cowork` for existing installs. The separate Claude plugin uses its own marketplace identifier.

## Setup

Open the plugin's **Connectors** tab, connect Pushary, and sign in with the same Pushary account used by your phone and Mac app. Enable Pushary in the conversation. If the connector is missing, add `https://pushary.com/api/mcp/mcp` under **Customize > Connectors > Add custom connector** and leave OAuth Client ID and Secret empty.

Follow [SETUP.md](SETUP.md) for account setup and verification. The connector uses OAuth; no local CLI, API key, or package installation is required.

Use the bundled skill to guide when Cowork asks questions and sends updates. You can also add standing instructions in **Settings > Cowork**. Ask Cowork a harmless Pushary test question, answer from your phone or notch, and verify Cowork receives the answer. A successful notification alone does not verify answers.

## Included

- `.mcp.json`: the public OAuth connector, with no embedded key.
- `skills/pushary-cowork/SKILL.md`: when to ask, notify, and hand off unanswered questions.
- `SETUP.md`: account setup, verification, and recovery.

## Capabilities

Cowork chooses when to call the tools. This bundle can wait for a question it asked and receive your answer on that request. It cannot intercept native permission prompts, send new work into an ended turn, or launch tasks. It installs no native hooks.

[Anthropic's platform support table](https://claude.com/docs/plugins/platform-support) describes what each app loads. The shared skill can also guide other Claude apps; use the separate Claude plugin's install instructions for those apps.

## Data sent to Pushary

Cowork sends the arguments of Pushary tool calls to `https://pushary.com/api/mcp/mcp`. These can include question text, answer options, notification titles and summaries, optional context, and agent and session identifiers. Pushary returns your answers to Cowork and delivers updates according to your account settings. Keep these messages brief and leave out passwords, API keys, file contents, and private conversation history. The plugin does not install a local process or upload a transcript automatically. See the [privacy policy](https://pushary.com/privacy) for storage and retention details.

[Full guide](https://pushary.com/docs/agents/guides/claude-desktop) · [Plugin support](https://support.claude.com/en/articles/13837440-use-plugins-in-claude) · [Pushary support](https://pushary.com/support)
