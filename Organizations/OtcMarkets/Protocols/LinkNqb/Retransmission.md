## LinkNqb Retransmission: TCP binary retransmission service for OTC Link NQB recovery

TCP binary retransmission service supporting recovery for the OTC extended-hours market data feeds (Depth of Book and Top of Book). Session-based flow: Login, Retransmission Request/Response, Spin Request/Response, Enhanced Spin Request/Response, Heartbeat. Delivers gap fills for sequenced UDP messages that a subscriber missed, plus spin/enhanced-spin snapshots for mid-session initialization. Used by OTC Link NQB, the daytime inter-dealer quotation system for OTC dealer-quoted equities.

### Overview

OTC Retransmission is the TCP-based recovery service that complements the OTC extended-hours multicast feeds. When a subscriber detects a sequence gap on the UDP Depth of Book or Top of Book channels — or wants a mid-session snapshot — it establishes a TCP session and issues Retransmission or Spin requests. The service is bilateral: request/response pairs plus Heartbeat during idle periods.

Two snapshot modes are supported: Spin (basic bootstrap of currently-known securities and orders) and Enhanced Spin (extended state including additional metadata). Both are used for mid-session initialization or full-state resynchronization. Used by OTC Link NQB; the daytime OTC Markets Multicast product uses a different Replay/Resend recovery mechanism.

### Transport

TCP stream carrying binary session messages framed by a 3-byte message header (MessageSize + MessageType) followed by payload. Byte-stream reassembly using MessageSize; no packet header. Session lifecycle: Login → Retransmission/Spin exchanges → Heartbeat during idle → disconnect.

### Key Characteristics

- **TCP session-based** - Login-bracketed TCP session with request/response message exchange
- **Gap-fill retransmission** - Retransmission Request/Response for recovering messages missed on the UDP multicast feeds
- **Spin snapshot recovery** - Spin Request/Response for basic mid-session bootstrap of currently-known state
- **Enhanced Spin** - Enhanced Spin Request/Response for extended-state initialization beyond basic Spin
- **Heartbeat monitoring** - Periodic Heartbeat messages during idle periods for connection health
- **Channel pairing** - Companion to the OTC Link NQB Depth of Book and Top of Book multicast channels

