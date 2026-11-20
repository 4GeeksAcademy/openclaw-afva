# Alfred - Custom Skills Design

## Objective

Design two reusable OpenClaw skills that extend Alfred's capabilities using existing Zapier MCP integrations.

Both skills must follow AGENTS.md and TOOLS.md.

## Skill 1: Document Assistant

### Purpose
Create structured Google Docs from user instructions, notes, or outlines.

### Inputs
- Document title
- Content or instructions
- Optional formatting requirements

### Workflow
1. Interpret the user's request.
2. Prepare structured document content.
3. Check whether the Google Docs creation tool is available through Zapier MCP.
4. Confirm authorization for the external action.
5. Create the document.
6. Verify the result and return its link.

### Expected Output
A Google Doc containing the requested information.

### Error Handling
If Google Docs is unavailable, provide the prepared content without claiming the document was created.

### Acceptance Test
Request a document containing a title, three sections, and a conclusion. Verify that the Google Doc exists and contains the expected content.

## Skill 2: Meeting Assistant

### Purpose
Create Google Calendar events from natural-language meeting requests.

### Inputs
- Meeting title
- Date
- Start time
- Duration or end time
- Time zone
- Optional description, location, and attendees

### Workflow
1. Extract the meeting details.
2. Request clarification for essential missing information.
3. Check Google Calendar availability through Zapier MCP.
4. Confirm authorization to create the event.
5. Create the calendar event.
6. Verify the event and return its details or link.

### Expected Output
A Google Calendar event matching the user's instructions.

### Error Handling
If the integration is unavailable or event creation fails, explain the problem without claiming success.

### Acceptance Test
Request a 30-minute test meeting. Verify its title, date, time, and duration in Google Calendar.

## Implementation Approach

- Use OpenClaw's native skill structure.
- Create one directory per skill.
- Include a SKILL.md file with clear activation instructions and workflows.
- Reuse existing Zapier MCP tools.
- Do not introduce additional API keys or paid services.
- Keep skill instructions concise and maintainable.

## Security and Authorization

- Follow AGENTS.md and TOOLS.md.
- Never store credentials in skill files.
- Do not assume integration availability.
- Do not perform unauthorized external actions.
- Never report unverified success.

## Development Plan

1. Review and commit this design.
2. Implement Document Assistant.
3. Implement Meeting Assistant.
4. Test both skills.
5. Document results.
6. Commit and push the completed implementation.