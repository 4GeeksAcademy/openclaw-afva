
# Alfred - Custom Skills Design

## Objective

Design two reusable OpenClaw skills that extend Alfred's capabilities using existing Zapier MCP integrations.

The skills are designed to reduce repetitive tasks, simplify interactions with Google Workspace, and produce useful outputs adapted to the user's professional context.

Both skills must follow the five configuration files:

- `IDENTITY.md`: Alfred's identity and presentation.
- `SOUL.md`: Personality, reasoning, and communication style.
- `AGENTS.md`: Operational rules, privacy, and authorization.
- `USER.md`: Professional context and user preferences.
- `TOOLS.md`: Available integrations and execution conventions.

---

## Skill 1: Document Assistant

### Purpose

Create structured Google Docs from user instructions, notes, or outlines.

### Design Rationale

Document creation is a recurring task in professional and technical work.

This skill reduces repetitive prompting by converting notes, outlines, and instructions into structured Google Docs.

The inputs are intentionally simple because users should not need to specify technical formatting or API parameters.

Google Docs was selected as the output because it provides an editable, shareable document that can be reused outside the conversation.

The skill uses the user's professional context and communication preferences from `USER.md` and `SOUL.md`, while respecting the authorization rules in `AGENTS.md` and integration guidance in `TOOLS.md`.

### Inputs

- Document title.
- Content, notes, outline, or instructions.
- Optional formatting requirements.
- Relevant context already available in the five configuration files.

The user can provide information in natural language without specifying technical parameters.

### Workflow

1. Interpret the user's request.
2. Identify the document's purpose, audience, and required structure.
3. Use relevant professional context and communication preferences.
4. Prepare structured document content.
5. Check whether the Google Docs creation tool is available through Zapier MCP.
6. Confirm authorization for the external action.
7. Create the document.
8. Verify the document's title and contents.
9. Return the verified Google Docs link.

### Expected Output

An editable Google Doc containing the requested information.

The document should:

- Have a clear title.
- Use a logical structure appropriate to its purpose.
- Reflect the user's professional context when relevant.
- Follow the user's preferred communication style.
- Avoid invented facts or unsupported claims.

The final response should include the document's URL and a brief confirmation of what was created.

### Error Handling

If Google Docs is unavailable, provide the prepared content without claiming the document was created.

If creation fails, explain the error clearly.

Never invent a document URL or report success without verification.

### Acceptance Test

Request a document containing a title, structured sections, and a conclusion.

Verify that the Google Doc exists and contains the expected content.

### Personalized Test

**Document title:** AI Engineering - Weekly Learning Notes

**Input:** Create a professional summary of the user's OpenClaw project, including custom skills, Zapier MCP, Telegram integration, lessons learned, and next steps.

**Expected result:** A structured Google Doc reflecting the user's AI Engineering project and communication preferences.

**Reported result:** Alfred confirmed creation and verification of the document.

**Evidence:**

https://docs.google.com/document/d/1niF-59nFXX7vXAhSrInC7ypwQoDM-17LWk8P0A3zxnc/edit

---

## Skill 2: Meeting Assistant

### Purpose

Create Google Calendar events from natural-language meeting requests.

### Design Rationale

Scheduling meetings requires translating natural-language requests into structured calendar information.

This skill eliminates the need to manually specify calendar fields and reduces errors involving dates, times, and time zones.

Natural-language input was selected because it matches how users normally describe meetings.

Google Calendar was selected because it produces an actionable, persistent event rather than a temporary text response.

The skill follows the user's preferences in `USER.md` and `SOUL.md`, while using `AGENTS.md` for authorization and `TOOLS.md` for integration-specific guidance.

### Inputs

- Meeting title.
- Date.
- Start time.
- Duration or end time.
- Time zone.
- Optional description.
- Optional location.
- Optional attendees.
- Calendar selection, when necessary.

The user can describe a meeting naturally without knowing the technical parameters required by Google Calendar.

### Workflow

1. Interpret the meeting request.
2. Extract the title, date, time, duration, and optional details.
3. Use available context and preferences where appropriate.
4. Request clarification when essential information is missing.
5. Check Google Calendar availability through Zapier MCP.
6. Identify the correct calendar.
7. Check whether a matching event already exists to avoid duplicates.
8. Confirm authorization to create the event.
9. Create the calendar event.
10. Verify its title, date, time, time zone, description, and attendees.
11. Return the verified event details and link.

### Expected Output

A Google Calendar event matching the user's instructions.

The event should:

- Have the correct title.
- Use the correct date and time zone.
- Have the requested duration.
- Include the specified description and attendees.
- Avoid unnecessary duplicates.

The final response should confirm the event details and provide its Google Calendar link.

### Error Handling

If essential information is missing, request clarification before creating the event.

If the calendar cannot be identified reliably, ask the user to select it.

If the integration is unavailable or event creation fails, explain the problem without claiming success.

Never invent an event link or create duplicate events unnecessarily.

### Acceptance Test

Request a 30-minute meeting.

Verify its title, date, start time, end time, and time zone in Google Calendar.

### Personalized Test

**Event title:** AI Engineering - OpenClaw Project Review

**Date:** November 26, 2026

**Time:** 17:00-17:30 Europe/Madrid

**Description:** Review the OpenClaw implementation, custom skills, Zapier MCP integrations, and outstanding requirements for the 4Geeks Academy assignment.

**Attendees:** None.

**Expected result:** A correctly scheduled event on the user's primary Google Calendar, with no duplicates.

**Reported result:** Alfred confirmed that the event was created and verified, with no matching event found before creation.

**Evidence:**

https://www.google.com/calendar/event?eid=aGFyY2xwdGMxdjBjamFpdTRkZW9hMWc0YmsgYW5kcmVzLnZhcmdhcy5hcmJvbGVkYUBt

---

## Implementation Approach

- Use OpenClaw's native skill structure.
- Create one directory per skill.
- Include a `SKILL.md` file with clear activation instructions and workflows.
- Reuse existing Zapier MCP tools.
- Do not introduce additional API keys, OAuth flows, or paid services.
- Keep skill instructions concise, modular, and maintainable.
- Separate the design documentation from the implementation.

### Repository Structure

```text
openclaw-afva/
├── IDENTITY.md
├── SOUL.md
├── AGENTS.md
├── USER.md
├── TOOLS.md
├── SKILLS_DESIGN.md
└── skills/
    ├── document-assistant/
    │   └── SKILL.md
    └── meeting-assistant/
        └── SKILL.md
```

---

## Security and Authorization

- Follow `AGENTS.md` and `TOOLS.md`.
- Never store credentials in skill files.
- Do not assume integration availability.
- Do not perform unauthorized external actions.
- Confirm consequential actions when required.
- Verify external results whenever possible.
- Never report unverified success.

---

## Development Plan

1. Review and commit the initial design.
2. Implement Document Assistant.
3. Implement Meeting Assistant.
4. Test both skills using existing Zapier MCP integrations.
5. Test personalization using the user's configuration files.
6. Document test results and evidence.
7. Commit and push the completed implementation.

---

## Project Verification

### Configuration

Five configuration files have been prepared and personalized.

### OpenClaw Doctor

- OpenClaw version: 2026.10.9.
- Diagnostic checks executed: 36.
- Reported errors: 0.
- Warnings: 2.

The warnings relate to loopback Gateway binding and the `TOOLS.md` migration recommendation.

### Skills

- Document Assistant: Implemented and functionally tested.
- Meeting Assistant: Implemented and functionally tested.

### Integrations

Both skills use the existing Zapier MCP connection.

No additional external API or OAuth configuration was introduced for this project.

### Personalization

Alfred successfully identified the user's professional background, interests, communication preferences, and critical-thinking expectations using `USER.md`.

### Verification Limitations

Google Docs and Google Calendar results were reported as verified by Alfred through the connected integrations.

The linked outputs have not been independently inspected as part of this documentation review.

---

## Conclusion

The project demonstrates how reusable OpenClaw skills can transform a general-purpose AI assistant into a personalized productivity tool.

Document Assistant simplifies professional document creation, while Meeting Assistant converts natural-language scheduling requests into structured calendar events.

Both skills use existing integrations, respect authorization boundaries, and are designed to produce practical, verifiable results.
