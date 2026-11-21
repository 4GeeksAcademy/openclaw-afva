---
name: meeting-assistant
description: Create Google Calendar events from natural-language meeting requests using an available, authorized Zapier MCP integration.
---

# Meeting Assistant

## Purpose

Convert natural-language meeting requests into Google Calendar events.

## Workflow

1. Identify the meeting title, date, start time, duration or end time, and time zone.
2. Extract optional details such as description, location, and attendees.
3. Ask for clarification only when essential information is missing or ambiguous.
4. Check whether a Google Calendar creation tool is available through Zapier MCP.
5. Verify the required parameters and confirm authorization for the external action.
6. Create the calendar event using the available tool.
7. Verify the event details against the user's request.
8. Return the event link or identifier and a brief confirmation.

## Rules

- Follow AGENTS.md and TOOLS.md.
- Never invent Google Calendar tool names or parameters.
- Never assume a date, time, or time zone when ambiguous.
- Never invite attendees or send notifications without authorization.
- Never create recurring events unless explicitly requested.
- Never claim an event was created without confirmation.
- If the integration is unavailable, provide the meeting details without claiming an event was created.
- Never expose credentials or confidential information.

## Testing

Create a test calendar event with:
- Title: Alfred Skill Test
- A specified date and start time
- Duration: 30 minutes
- Time zone: Europe/Madrid

Verify the event exists and that its title, date, time, and duration match the request.