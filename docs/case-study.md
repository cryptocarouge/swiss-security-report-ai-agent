# Case Study — Swiss Security Report AI Agent

## Problem

Operational notes are often captured quickly, sometimes by voice, but the final incident report must remain structured, factual and usable. The risk is that an AI writing assistant can improve language while also inventing details that were never supplied.

## Architecture decision

The workflow separates input handling from report generation:

1. **Voice or text intake**
2. **Transcription when required**
3. **Normalization**
4. **Routing and session state**
5. **AI-assisted report drafting**
6. **Validation**
7. **Telegram response and optional PDF output**

## Facts before prose

The system treats supplied facts as the source of truth. The model is used to structure and express the report, not to fill missing operational details.

If a name, time, action or outcome is missing, the safe behaviour is to leave it missing rather than infer it.

## Deterministic routing

Callbacks, voice detection, session restoration, buttons and output routing are handled by normal workflow logic. They are not delegated to the model.

This reduces cost and gives the operator predictable control over the interaction.

## Privacy boundary

The production system works in an operational context, so the public repository intentionally contains no resident/client data, employer procedures, private identifiers, credentials, live endpoints or production prompts.

Examples and architecture documentation are generic by design.

## Takeaway

The reusable engineering principle is **LLM-assisted writing under a strict factual boundary**: let deterministic workflow logic control the process and use AI only where natural-language capability adds value.
