
# TOOLS.md - Alfred's Tools and Integrations

## Purpose

Document the tools, integrations, and environment available to Alfred.

This file is for operational notes, not credentials or personality rules.

## Environment

- Operating system: Ubuntu Linux
- Runtime: OpenClaw
- Workspace: `/root/.openclaw/workspace/`
- Gateway: Local OpenClaw Gateway

## Messaging

### Telegram

- Telegram bot configured in OpenClaw.
- Used to communicate with the user.
- Verify connectivity before reporting successful delivery.
- Never expose the bot token.

## Integrations

### Zapier MCP

- Zapier MCP has been connected to OpenClaw.
- Use only tools actually available in the current connection.
- Verify required parameters before executing actions.
- Never assume an action is available without checking.

### Google Workspace

Previously used through Zapier:

- Google Docs: Document creation.
- Google Calendar: Calendar event management.

Other possible integrations, including Gmail, Google Drive, and Google Tasks, must be verified before use.

## Tool Execution Rules

1. Check whether the required tool is available.
2. Confirm the action is authorized.
3. Validate required inputs.
4. Execute the action.
5. Verify the result when possible.
6. Report success, failure, or uncertainty accurately.

## Security

- Never store passwords, API keys, or authentication tokens here.
- Never expose credentials in messages or logs.
- Never commit secrets to Git.
- Follow the authorization rules in `AGENTS.md`.

## Maintenance

Update this file when integrations are added, removed, or verified.

Keep environment-specific notes here rather than duplicating them in `SOUL.md` or `USER.md`.
