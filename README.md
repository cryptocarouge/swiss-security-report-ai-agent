# Swiss Security Report AI Agent

A privacy-first AI automation project for turning voice or text input into structured professional incident reports in French.

This repository is a clean public portfolio edition. The production workflow and all organisation-specific procedures remain private.

## What it demonstrates

- Telegram voice or text input
- Audio transcription
- Input normalization
- AI-assisted report drafting
- Structured operational output
- Session continuity
- Callback/button routing
- PDF generation through Gotenberg
- Separation between workflow logic and LLM tasks
- Anti-hallucination constraints: missing facts should not be invented

## Architecture

```text
Voice / Text
     |
     +--> Transcription
     |
     v
Normalize Input
     |
     v
Routing / State
     |
     v
AI Report Agent
     |
     v
Validation
     |
     +--> Telegram Output
     |
     +--> PDF Generation
```

## Design principles

1. **Facts first** — the system works from supplied information.
2. **Deterministic routing first** — conditions, callbacks and state are handled by workflow logic where possible.
3. **AI only where useful** — transcription, interpretation and report drafting.
4. **Privacy by design** — real resident/client data is never part of the public repository.
5. **Operational output** — the goal is a usable report, not a generic chatbot response.

## Security boundary

Not published:

- API keys or tokens
- Telegram chat IDs
- Private webhook URLs
- Employer-specific instructions
- Personal/resident information
- Production prompts
- Production workflow JSON

## Disclaimer

Independent personal automation project. It is not an official product of, nor affiliated with, any security company or public authority.
