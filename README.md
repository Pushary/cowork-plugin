# Pushary for Cowork

[![Plugin checks](https://github.com/Pushary/cowork-plugin/actions/workflows/plugin-check.yml/badge.svg)](https://github.com/Pushary/cowork-plugin/actions/workflows/plugin-check.yml)

Get Cowork task updates and answer its questions from your phone or Mac. This plugin connects Cowork to your Pushary account.

## Before you install

The plugin source is MIT-licensed. Phone and Mac delivery use the hosted Pushary service, which requires a [Pushary plan](https://pushary.com/pricing) and a connected device. Install [Pushary on your phone or Mac](https://pushary.com/download) and use the same account when connecting Claude. The hosted backend is not included in this repo.

Chat and Cowork plugins require a paid Claude plan. See [Claude’s supported plans and apps](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

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

## What it can do

The shared skill guides when Cowork asks questions and sends updates. Cowork chooses when to call these tools. The plugin can receive an answer to a question it asked; it does not intercept native permission prompts, start new tasks, or resume an ended turn. It installs no native hooks.

For Claude Chat or Claude Code, use [Pushary for Claude](https://github.com/Pushary/claude-plugin). Both packages use the same shared skill and connector. Choose one Pushary installation per app to avoid duplicate tools.

## Verification

[CI](https://github.com/Pushary/cowork-plugin/actions/workflows/plugin-check.yml) validates both manifests with pinned Claude Code, installs the checked-out package in an isolated profile, and checks its version, loaded skill, lack of native hooks, and OAuth connector configuration. Changes run on Linux; releases and manual checks also run on macOS and Windows. No account credentials are used.

CI does not test account OAuth or device delivery. Verify those with the [setup checks](SETUP.md#4-verify-both-directions). Directory review is separate; this GitHub release is not an approved Claude directory listing.

## Privacy and contributing

Cowork sends the arguments of Pushary tool calls to the hosted connector: questions, answer options, updates, optional context, and agent or session identifiers. Keep secrets, file contents, and private conversation history out of these messages. The plugin does not upload a transcript automatically. Read the [privacy policy](https://pushary.com/privacy) for retention details.

[Report a bug](https://github.com/Pushary/cowork-plugin/issues/new/choose) · [Contribute](CONTRIBUTING.md) · [Security reports](https://github.com/Pushary/.github/blob/main/SECURITY.md) · [Support](https://pushary.com/support) · [Full guide](https://pushary.com/docs/agents/guides/claude-desktop)
