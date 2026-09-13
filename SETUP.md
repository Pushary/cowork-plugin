# Set up Pushary for Claude Desktop and Cowork

## 1. Add the connector

Install the Pushary Cowork plugin, or add this public URL in Claude under **Customize > Connectors > Add custom connector**:

```text
https://pushary.com/api/mcp/mcp
```

Leave OAuth Client ID and Secret empty. Sign in with the same Pushary account used by your phone and Mac app. The link contains no key. On versions where installing the plugin does not add its connector, add the URL manually.

You can print these steps from any terminal with `npx @pushary/agent-hooks@latest cowork`. `setup --agents cowork` uses the same path and does not install CLI hooks, save a CLI key, or start a daemon. Printing the steps does not mean your account is connected.

## 2. Enable tools in the task

In a Chat or Cowork conversation, enable Pushary under **Customize > Connectors**. Claude may ask you to allow its tool calls. If it repeatedly asks permission, check the controls available for that version and your organization’s policy; this setup cannot bypass them.

## 3. Guide proactive use

Use the bundled Cowork skill or paste the output of `pushary cowork --instructions` into **Settings > Cowork**. To upload the skill separately, run `pushary cowork --skill > SKILL.md`, place it in a folder, zip that folder, and upload through Claude’s skill settings. Do not rely on a repository’s CLAUDE.md or AGENTS.md for this connector setup.

## 4. Verify both directions

Ask Claude to use Pushary `ask_user` with type `confirm` for a harmless setup question. Use agentName `Claude Cowork - Setup check` in Cowork or `Claude Chat - Setup check` in Chat. Answer from Pushary and verify Claude reports the answer it received. Test the notch and phone separately, including phone delivery while away from your Mac.

If nothing arrives, check the signed-in account, task-level connector enablement, tool permission, and Pushary delivery mode. CLI `doctor` checks your local CLI installation, not this account-level connector. Remove a connector from Claude to disconnect it; CLI clean does not remove account connectors.

## Supported boundary

The connector can notify and ask; it does not intercept native permission prompts or restart an ended Cowork turn. Cowork supports plugin hooks on supported versions, but this package does not install or verify them. Both local and cloud Cowork tasks can use the remote connector. A native task being open on your Mac does not prove Pushary can stop or message it.
