# Coding Agent Protocol (CAP)

**One protocol to drive every coding agent CLI.**

Coding agent CLIs are everywhere — [Claude Code](https://github.com/anthropics/claude-code), Codex CLI, Gemini CLI, and more keep shipping. But each one speaks its own dialect: different invocation flags, different session models, different streaming formats. Every web or desktop app that wants to orchestrate them has to integrate each agent one by one.

**CAP fixes that.** It is an open, standard protocol that lets web and desktop applications discover, connect to, and operate any local coding agent CLI through a single interface.

## How it works

```
┌─────────────────────┐         ┌──────────────────────────────┐
│  Web / Desktop App  │  ◄CAP►  │  Local Listener (daemon)     │
│  (client)           │         │  ├─ adapter: claude-code     │
└─────────────────────┘         │  ├─ adapter: codex-cli       │
                                │  └─ adapter: gemini-cli      │
                                └──────────────────────────────┘
```

- **Adapters** — a thin, uniform wrapper for each agent CLI, translating CAP messages into the agent's native commands and back.
- **Listener** — a local daemon that detects which agent CLIs are installed and exposes them to clients over the protocol.
- **Clients** — web apps and desktop software that create sessions, dispatch tasks, stream output, and manage agent lifecycles — without caring which agent is underneath.

## Status

🚧 **Early design phase.** The protocol spec and reference implementation are under active development in this organization. Watch this space — or open a discussion if you'd like to get involved.

---

*Building an agent CLI or an app that orchestrates one? We'd love your input on the spec.*
