# Engineering Challenges

## 1. Transport mismatch between client and server

**Problem.** The React client uses socket.io-client; the backend offers only a plain WebSocket route and REST, so the chat could not connect.

**Approach.** Rather than rewrite either side, a thin python-socketio ASGI wrapper mounts the original FastAPI app unchanged and handles the client's `message` event. It emits `typing` before the reply and `bot_response` (text plus quick replies) after, calling the existing message handler directly.

**Result.** The chat runs end to end with the original reply logic. A production path would implement Socket.IO natively in the service or switch the client to plain WebSocket.

## 2. A conversational engine too heavy to run alongside the UI

**Problem.** The Rasa setup needs an older Python version plus database and cache services.

**Approach.** The runnable path uses the minimal keyword-based backend. The Rasa configuration and wrapper remain in the codebase, documented but not run.

**Result.** The demo starts quickly and its behaviour is deterministic. It is honest to call it rule-based, not AI.

## 3. Unfinished sections in a navigable UI

**Problem.** The navigation lists Courses, Booking, FAQ, Analytics and Admin, which are not built.

**Approach.** Each route renders a simple "coming soon" card so navigation never lands on a broken page. They are placeholders and are not shown as features.

## 4. Broken dependencies in the checked-in project

**Problem.** The committed node_modules directory was unusable.

**Approach.** Dependencies were reinstalled from the lockfile with a clean install, with no version upgrades.

## 5. Documentation versus implementation drift

**Problem.** The original README lists capabilities and infrastructure that the code does not contain.

**Approach.** The portfolio documents describe only what was verified by running the build or reading the code, and call out the rest as planned.
