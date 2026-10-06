# Technical Case Study

## Goal

Explore a support assistant for education companies: a polished chat front end, a real-time backend, and a path toward a trained conversational engine (Rasa).

## Decisions

- **Material UI plus a custom theme.** Gives a consistent, responsive, accessible component base. For the portfolio build the visual layer (palette, typography, landing and chat styling) was refreshed without changing behaviour.
- **Socket.IO on the client.** Chosen for reconnects and event semantics; the chat is built around `message`, `typing` and `bot_response` events.
- **Rule-based replies for the runnable path.** The simple backend answers by keyword so the system runs with no external services.
- **Rasa kept as the intended NLU path.** Intents, stories and a domain exist in the repo; the integration code was not run.

## What is solid

- A clean separation between UI, transport and reply logic, which makes the reply engine swappable.
- A usable chat UI: quick replies, typing state, settings drawer, full-screen mode, mobile layout.
- Backend building blocks (WebSocket manager, middleware, Docker files) written for a fuller deployment.

## Limits and trade-offs

- Replies are keyword lookups with a handful of canned answers; there is no language understanding, memory or learning.
- Five of the seven sections in the navigation are placeholders.
- The original frontend and backend disagreed on transport (Socket.IO vs plain WebSocket), so the demo uses a bridge.
- Voice input, sentiment analysis, multi-language replies, CRM and calendar integrations are not implemented.
- Original project notes mention technologies (for example Kafka, Elasticsearch, Kubernetes) that are not present in the code.
- No automated test run was performed for this portfolio build.

## Changes for the portfolio build

- One original source edit: the socket URL in the chat component reads an environment variable with the original value as the fallback.
- Visual styling refresh (theme/CSS/landing/navbar/footer polish), with originals backed up.
- A separate demo server file for the Socket.IO bridge. None of this is part of the public repository.
