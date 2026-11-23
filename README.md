# Pushary for Cowork

[![Plugin checks](https://github.com/Pushary/cowork-plugin/actions/workflows/plugin-check.yml/badge.svg)](https://github.com/Pushary/cowork-plugin/actions/workflows/plugin-check.yml)

Get Cowork task updates and answer its questions from your phone or Mac. This plugin connects Cowork to your Pushary account.

## Before you install

The plugin source is MIT-licensed. Phone and Mac delivery use the hosted Pushary service, which requires a [Pushary plan](https://pushary.com/pricing?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme) and a connected device. Install [Pushary on your phone or Mac](https://pushary.com/download) and use the same account when connecting Claude. The hosted backend is not included in this repo.

Chat and Cowork plugins require a paid Claude plan. See [Claude’s supported plans and apps](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

## What you get after you sign in

1. Sign in and pick a plan. New customers start with a 3-day trial.
2. Install this plugin and connect Pushary with the same account. There is no CLI to run and no API key to copy.
3. When Cowork needs an answer from you, the question arrives on your phone (the Pushary app for iOS and Android), on your Mac, or in the dashboard. A question from Cowork stays open for 10 minutes.
4. You answer with one tap, or type a short reply, and Cowork carries on. The dashboard keeps a record of what each agent asked and what you answered.

See [Claude Cowork notifications on your phone](https://pushary.com/claude-cowork-notifications?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme), or read the [Claude and Cowork guide](https://pushary.com/docs/agents/guides/claude-desktop?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme).

## Plans

Each plan starts with a 3-day trial for new customers. During the trial, Agent, Agent Pro and Team include 5 call minutes.

| Plan | Price | What you get |
| --- | --- | --- |
| [Agent](https://pushary.com/pricing?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme) | $9.99 a month | One person and every AI agent they run. Approve, deny or answer from your phone or Mac. 10 call minutes a month. |
| [Agent Pro](https://pushary.com/pricing?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme) | $19.99 a month | Everything in Agent, plus unlimited notifications, budgets and priority support. 20 call minutes a month. |
| [Team](https://pushary.com/teams?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme) | $59 a month for 5 people, $12 for each extra person | A shared record of what your team's agents asked and who answered, with export. 60 call minutes a month. |

Missed the push? Pushary can call you, by default after 1 minute, and read the request. You approve it, say no or tell the agent what to do. Calls need a confirmed phone number and work in English, German, French and Dutch. [Phone calls](https://pushary.com/calls?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme) · [Calls for Cowork](https://pushary.com/claude-cowork-phone-call?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme) · [How calls work](https://pushary.com/docs/agents/phone-calls?utm_source=github&utm_medium=oss-adapter&utm_campaign=cowork-plugin&utm_content=readme)

## Install and connect

In Cowork, open **Customize > Plugins > Add > Add marketplace**, add `https://github.com/Pushary/cowork-plugin`, and install **Pushary for Cowork**.

Connect Pushary from the plugin's **Connectors** tab and enable it in the conversation. You can also add standing instructions in **Settings > Cowork**.

Existing installs keep the plugin name `pushary`, marketplace name `pushary-claude`, and skill identifier `pushary-cowork`.

If your Claude version does not add the connector, add `https://pushary.com/api/mcp/mcp` under **Customize > Connectors > Add custom connector**. Leave OAuth Client ID and Secret empty. No Pushary CLI or API key is needed for this setup. See [SETUP.md](SETUP.md) for verification and recovery.

## Try it

Ask Cowork:

```text
Use Pushary to ask which summary format I want: bullets or a paragraph.
Wait for my answer and use that format.
```

Answer from your phone or Mac and check that Cowork receives the answer. Then try:

```text
When you finish this task, send me a Pushary notification with the result.
```

[Hear a real Claude Code approval call](https://pushary.com/calls?utm_source=github&utm_medium=readme&utm_campaign=phone_answer&utm_content=cowork_call#recorded-claude-code-call) or [try the three-agent exercise](https://github.com/Pushary/pushary-skill/blob/main/examples/which-agent-is-waiting.md).

## What it can do

The shared skill guides when Cowork asks questions and sends updates. Cowork chooses when to call these tools. The plugin can receive an answer to a question it asked; it does not intercept native permission prompts, start new tasks, or resume an ended turn. It installs no native hooks.

For Claude Chat or Claude Code, use [Pushary for Claude](https://github.com/Pushary/claude-plugin). Both packages use the same shared skill and connector. Choose one Pushary installation per app to avoid duplicate tools.

## Verification

[CI](https://github.com/Pushary/cowork-plugin/actions/workflows/plugin-check.yml) validates both manifests with pinned Claude Code, installs the checked-out package in an isolated profile, and checks its version, loaded skill, lack of native hooks, and OAuth connector configuration. Changes run on Linux; releases and manual checks also run on macOS and Windows. No account credentials are used.

CI does not test account OAuth or device delivery. Verify those with the [setup checks](SETUP.md#4-verify-both-directions). Directory review is separate; this GitHub release is not an approved Claude directory listing.

## Related repositories

- [Pushary for Claude](https://github.com/Pushary/claude-plugin): the same skill and connector for Claude Chat and Claude Code.
- [Pushary skill](https://github.com/Pushary/pushary-skill): Claude Code approval hooks through `npx -y pushary@latest setup`.
- [Pushary for Mac](https://github.com/Pushary/pushary-mac): answer from the notch on your Mac.

## Privacy and contributing

Cowork sends the arguments of Pushary tool calls to the hosted connector: questions, answer options, updates, optional context, and agent or session identifiers. Keep secrets, file contents, and private conversation history out of these messages. The plugin does not upload a transcript automatically. Read the [privacy policy](https://pushary.com/privacy) for retention details.

[Report a bug](https://github.com/Pushary/cowork-plugin/issues/new/choose) · [Contribute](CONTRIBUTING.md) · [Security reports](https://github.com/Pushary/.github/blob/main/SECURITY.md) · [Support](https://pushary.com/support) · [Full guide](https://pushary.com/docs/agents/guides/claude-desktop)
