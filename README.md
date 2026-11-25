# AgentHub Personal Assistant (Discord + Switch + Codex)

A personal AI teammate for a private Discord server. It helps with planning, reminders-as-drafts, study explanations, daily organization, and conversation summaries.

## Architecture

Discord channel ↔ Switch Discord integration ↔ Switch room ↔ Codex agent

**Important:** Switch owns the Discord connection and agent routing. This starter does not create a second Discord bot or pretend to implement undocumented Switch APIs.

## Requirements

- Windows 11
- Docker Desktop with WSL 2 backend
- Switch Console
- Codex provider/connector supported by your installed Switch version
- A private Discord test server and channel (for example `#personal-assistant`)

## Setup

1. Extract this folder to a location you can find, such as `C:\Users\<you>\Desktop\AgentHub-Personal-Assistant`.
2. Open Switch Console and follow its current Windows onboarding to start a local Switch server. Docker Desktop must be running.
3. In Switch Console, configure the Codex provider and its Switch connector using the in-app provider setup. Sign in as prompted.
4. Create an agent named `PersonalAssistant`.
   - Provider: Codex
   - Working directory: this project folder
   - Instructions: paste the contents of `agent/AGENTS.md`
5. Connect Discord through Switch's supported messaging-app connection flow. Use a private test server and a dedicated channel such as `#personal-assistant`.
6. Create a Switch room connected to that Discord channel and attach `PersonalAssistant`.
7. Use the test prompts in `docs/test-prompts.md`.

Exact labels can differ by Switch release. Follow the installed Console's current onboarding rather than guessing at menu names.

## Optional Codex CLI for editing this project

Install Codex CLI using the official OpenAI instructions, then open PowerShell in this folder and run `codex`. Ask it to inspect `AGENTS.md` and improve the starter. Review proposed changes before accepting them.

## Scope and limitations

- This project supplies assistant behaviour, workflows, and test cases.
- It does not claim to create persistent reminders, send emails, access calendars, or browse the web unless those capabilities are separately connected and explicitly enabled.
- For reminders, it can draft a reminder plan; a real scheduled reminder requires an approved scheduling integration.
- Never put Discord tokens, API keys, or passwords in project files or GitHub.
- Keep the Discord server private while testing. Restrict who can invoke the agent.
- Require approval before deleting files, changing settings, making purchases, or sending messages outside the test room.
