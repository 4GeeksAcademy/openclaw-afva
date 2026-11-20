---
name: document-assistant
description: Create structured Google Docs from user instructions using an available, authorized Zapier MCP integration.
---

# Document Assistant

## Purpose

Create well-structured Google Docs from notes, outlines, or natural-language instructions.

## Workflow

1. Understand the requested document's purpose, title, content, and format.
2. Ask for clarification only when essential information is missing.
3. Prepare the document with appropriate headings, sections, and content.
4. Check whether a Google Docs creation tool is currently available through Zapier MCP.
5. Verify the required parameters and confirm authorization for the external action.
6. Create the Google Doc using the available tool.
7. Verify the creation result and, when possible, the document content.
8. Return the document link and a brief confirmation.

## Rules

- Follow AGENTS.md and TOOLS.md.
- Never invent Google Docs tool names or parameters.
- Never claim a document was created without confirmation.
- If the integration is unavailable, provide the prepared document content instead.
- Never expose credentials or confidential information.
- Do not share the document with additional people unless authorized.

## Testing

Create a test document containing:
- A title
- Three sections
- A conclusion

Verify the document exists and contains the expected information.