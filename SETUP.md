# Set up Pushary for Cowork

## 1. Add the connector

Install **Pushary for Cowork** as described in [README.md](README.md). Open the plugin's **Connectors** tab and connect Pushary. You can also add this public URL under **Customize > Connectors > Add custom connector**:

```text
https://pushary.com/api/mcp/mcp
```

Leave OAuth Client ID and Secret empty. Sign in with the same Pushary account used by your phone and Mac app. The link contains no key. On versions where installing the plugin does not add its connector, add the URL manually.

No local CLI, API key, or package installation is required. Setup is complete only after Cowork receives your answer to the test in step 4.

## 2. Enable tools in the task

In the Cowork conversation, enable Pushary under **Customize > Connectors**. Cowork may ask you to allow its tool calls. If it repeatedly asks permission, check the controls available for that version and your organization’s policy; this setup cannot bypass them.

## 3. Guide proactive use

Use the bundled skill. You can also add standing instructions in **Settings > Cowork** to ask for missing decisions and send task updates while you are away. Cowork does not rely on a repository’s CLAUDE.md or AGENTS.md for this connector setup.

## 4. Verify both directions

Ask Cowork to use Pushary `ask_user` with type `confirm` for a harmless setup question. Use agentName `Claude Cowork - Setup check`. Answer from Pushary and verify Cowork reports the answer it received. Test the notch and phone separately, including phone delivery while away from your Mac.

If nothing arrives, check the signed-in account, task-level connector enablement, tool permission, and Pushary delivery mode. CLI `doctor` checks your local CLI installation, not this account-level connector. Remove a connector from Cowork to disconnect it; CLI clean does not remove account connectors.

## Supported boundary

The connector can notify and ask; it does not intercept native permission prompts or restart an ended turn. This package installs no native hooks. A task being open on your Mac does not prove this connector can stop or message it.

For Claude Chat and Claude Code, use the separate [Pushary for Claude plugin](https://github.com/Pushary/claude-plugin). Choose one Pushary plugin per app to avoid duplicate connectors.
