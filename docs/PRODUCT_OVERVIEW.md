# Product Overview

ChatbotX is a prototype support-assistant for education providers: a React landing page and a real-time chat interface, backed by a small FastAPI service. It is an early-stage build, not a finished product, and this overview separates what works from what is only planned.

## What works in the demo build

- **Landing page.** Hero, feature cards, technology list and call-to-action, with a responsive layout.
- **Chat interface.** Message bubbles, a typing indicator, quick-reply chips, a settings drawer (language selector, feedback entry), a full-screen toggle and browser text-to-speech playback of bot replies.
- **Real-time transport.** The chat talks to the backend over Socket.IO.
- **Responsive layout.** Landing page and chat adapt to phone widths.

## How the chat replies

The replies come from a **rule-based keyword matcher** (a small set of canned answers for topics such as courses, enrollment and pricing). No LLM or hosted AI service is called and the demo contains no machine-learning model. A Rasa 3 configuration (intents, stories, domain) and a service wrapper are present in the codebase, but they were not run for this build.

## Planned or placeholder

- Courses, Booking, FAQ, Analytics and Admin pages are "coming soon" placeholder cards.
- Voice input, sentiment analysis, multi-language replies, CRM and calendar integration are described in the original project notes but are stubs or not implemented.
- Marketing figures on the landing page (response time, accuracy, uptime, compliance wording) are placeholder copy, not measurements.

## Demo data

The demo has no accounts and stores no user data. Screenshots show a local build with fictional placeholder content.
