<div align="center">

# ChatbotX

**A prototype support assistant for education providers: a responsive landing page and a real-time chat interface with quick replies.**

React · TypeScript · Material UI · Socket.IO · FastAPI

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Material UI](https://img.shields.io/badge/Material%20UI-5-007FFF?logo=mui&logoColor=white)
![Redux Toolkit](https://img.shields.io/badge/Redux%20Toolkit-764ABC?logo=redux&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-010101?logo=socketdotio&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)

<table>
  <tr>
    <td><img src="assets/screenshots/chatbotx-landing-hero.webp" width="480" alt="ChatbotX landing page hero with navigation and call-to-action buttons" /></td>
    <td><img src="assets/screenshots/chatbotx-chat-conversation.webp" width="480" alt="Chat window with user messages, bot replies and quick-reply chips" /></td>
  </tr>
</table>
<sub>Screenshots are real captures of a local build running on fictional demo data.</sub>

</div>

---

## Product at a Glance

| | |
|---|---|
| **What it is** | Landing page and chat UI for an education-support assistant |
| **Chat engine** | Rule-based keyword replies. No LLM and no trained model in the demo |
| **Frontend** | React 18, TypeScript, Material UI 5, Redux Toolkit, Framer Motion |
| **Transport** | Socket.IO (typing and reply events) |
| **Backend** | FastAPI service with keyword matching |
| **Status** | Early prototype. Several sections are placeholders |

## Product Showcase

<table>
  <tr>
    <td><img src="assets/screenshots/chatbotx-chat-welcome.webp" width="400" alt="Chat welcome message with quick-reply options" /><br/><sub>Chat welcome state with quick replies</sub></td>
    <td><img src="assets/screenshots/chatbotx-chat-settings.webp" width="400" alt="Chat settings drawer with language and feedback options" /><br/><sub>Settings drawer</sub></td>
  </tr>
  <tr>
    <td><img src="assets/screenshots/chatbotx-chat-fullscreen.webp" width="400" alt="Full-screen chat conversation" /><br/><sub>Full-screen chat</sub></td>
    <td>
      <img src="assets/screenshots/chatbotx-mobile-landing.webp" width="150" alt="Landing page at phone width" />
      <img src="assets/screenshots/chatbotx-mobile-chat.webp" width="150" alt="Chat at phone width" /><br/><sub>Phone-width layouts</sub>
    </td>
  </tr>
</table>

## Key Features

- Landing page with hero, feature cards and technology list.
- Chat with message bubbles, typing indicator and quick-reply chips.
- Settings drawer with language selector and feedback entry.
- Full-screen chat mode and responsive layout down to phone width.
- Browser text-to-speech playback of bot replies.
- Socket.IO event flow (`message`, `typing`, `bot_response`).

## Architecture

- React single-page app talks to the backend over Socket.IO.
- The runnable backend is a small FastAPI app answering by keyword rules.
- A thin Socket.IO bridge wraps that app because the original backend exposed only plain WebSocket.
- A fuller backend (MongoDB, Redis, WebSocket manager) and a Rasa 3 project exist in the codebase but were not run.

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Engineering Highlights

- Resolved a client/server transport mismatch with a roughly 30-line bridge, leaving the original backend untouched.
- Reply logic is separated from transport and UI, so the keyword engine can be swapped for an NLU engine.
- Responsive Material UI theme with a custom palette and typography.
- Backend building blocks written for a larger deployment: WebSocket rooms and broadcast, rate-limit and logging middleware, Docker files (read, not run).
- Rasa intent, story and domain files prepared as the intended NLU path (not run).

## Status and Scope

- **Real:** landing page, chat UI, Socket.IO event flow, keyword-based replies, browser speech synthesis.
- **Rule-based:** all replies. There is no AI model, LLM or external API behind the chat.
- **Placeholders:** Courses, Booking, FAQ, Analytics and Admin are "coming soon" cards.
- **Not implemented:** voice input, sentiment analysis, multi-language replies, CRM and calendar integration.
- **Landing copy:** figures such as response time, accuracy, uptime and compliance wording are placeholder marketing text, not measured results.
- The demo runs locally with no accounts and no stored user data.

## Documentation

- [Product Overview](docs/PRODUCT_OVERVIEW.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Technical Case Study](docs/TECHNICAL_CASE_STUDY.md)
- [Engineering Challenges](docs/ENGINEERING_CHALLENGES.md)
- [Privacy and Source](docs/PRIVACY_AND_SOURCE.md)

## Source Code

The source is private and no licence is granted. See [RIGHTS.md](RIGHTS.md).
