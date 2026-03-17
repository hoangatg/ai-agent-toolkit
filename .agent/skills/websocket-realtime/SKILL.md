---
name: websocket-realtime
description: Real-time communication patterns. WebSockets, Server-Sent Events, Socket.io, and live collaboration. Use when building chat, notifications, live dashboards, or multiplayer features.
---

# WebSocket & Real-time

> When polling isn't fast enough, push.

---

## 1. Technology Selection

| Technology | Direction | Best For |
|-----------|-----------|----------|
| **WebSocket** | Bidirectional | Chat, gaming, collaboration |
| **SSE (Server-Sent Events)** | Server → Client | Notifications, live feeds |
| **Long Polling** | Simulated push | Legacy browser support |
| **WebRTC** | Peer-to-peer | Video, audio, P2P data |
| **WebTransport** | Bidirectional (HTTP/3) | Next-gen, bleeding edge |

### Decision Matrix

```
Need bidirectional? → WebSocket
Server push only?  → SSE (simpler, auto-reconnect)
P2P media?         → WebRTC
Legacy support?    → Long Polling (fallback)
```

---

## 2. WebSocket Patterns

### Libraries

| Library | Ecosystem | Features |
|---------|-----------|----------|
| **Socket.io** | Node.js | Rooms, namespaces, fallback |
| **ws** | Node.js (raw) | Lightweight, no overhead |
| **Pusher/Ably** | Managed | Hosted, scaled for you |
| **Supabase Realtime** | Supabase | Postgres changes live |

### Room/Channel Pattern

| Concept | Purpose |
|---------|---------|
| **Rooms** | Group connections by context (chat room, game) |
| **Namespaces** | Separate concerns (chat vs notifications) |
| **Broadcasting** | Send to all in room except sender |

---

## 3. Scaling WebSockets

| Challenge | Solution |
|-----------|---------|
| **Sticky sessions** | Load balancer affinity |
| **Multi-server** | Redis pub/sub adapter |
| **Connection limits** | Horizontal scaling + connection pooling |
| **State sync** | CRDT or operational transforms |

---

## 4. Reliability Patterns

| Pattern | Purpose |
|---------|---------|
| **Heartbeat/Ping** | Detect dead connections |
| **Auto-reconnect** | Exponential backoff on disconnect |
| **Message queue** | Buffer during disconnection |
| **Acknowledgments** | Confirm message delivery |
| **Idempotency** | Handle duplicate messages |

---

## 5. Live Collaboration

| Pattern | Use Case |
|---------|----------|
| **CRDT** | Conflict-free concurrent editing |
| **OT (Operational Transform)** | Google Docs-style collaboration |
| **Last Write Wins** | Simple, some data loss OK |

### Libraries

| Library | Purpose |
|---------|---------|
| **Yjs** | CRDT framework for collaboration |
| **Liveblocks** | Managed collaboration infrastructure |
| **PartyKit** | Edge-based real-time platform |

---

## 6. Security

| Concern | Solution |
|---------|---------|
| **Auth** | Authenticate on connection (token in handshake) |
| **Authorization** | Check room access on join |
| **Rate limiting** | Limit messages per second per client |
| **Input validation** | Validate every incoming message |
| **Origin check** | Restrict allowed origins |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| WebSocket for everything | Use REST for CRUD, WS for real-time only |
| No reconnection logic | Auto-reconnect with backoff |
| Trust client messages | Validate and sanitize server-side |
| Store state in connections | External state (DB/Redis) |
| Ignore connection limits | Plan for max concurrent connections |

---

> **Remember:** Real-time adds complexity. Use it when users need instant feedback. For everything else, REST + polling is simpler and more reliable.
