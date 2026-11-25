# Architecture

```text
User in private Discord channel
          |
          v
Switch Discord messaging integration
          |
          v
Switch room and agent routing
          |
          v
Codex-backed PersonalAssistant agent
          |
          v
Response posted back to Discord
```

Switch handles the Discord transport and routes room messages to the configured agent. The Codex agent follows `agent/AGENTS.md` and the relevant skill files. There is deliberately no second custom Discord bot in this starter.
