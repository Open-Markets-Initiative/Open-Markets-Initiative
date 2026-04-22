## CommonClient: Pillar TCP framing and session layer

NYSE Pillar's shared client-facing session and framing header, serving as the message envelope beneath Pillar BinaryGateway order entry and other client-to-exchange protocols across NYSE, NYSE American, NYSE Arca, NYSE National, NYSE Texas, and NYSE options markets.

### Overview

CommonClient is the unified client-side session layer introduced with NYSE's Pillar trading platform to replace the venue-specific gateways that preceded it. By consolidating session establishment, sequencing, heartbeats, and framing behind a single specification, Pillar lets a single client build interoperate with NYSE cash equities, NYSE American, NYSE Arca, NYSE National, NYSE Texas, and the NYSE options exchanges using identical session semantics and differing only in the application payloads they carry.

Each CommonClient session begins with a Logon exchange that authenticates the client, negotiates session identity, and establishes the starting sequence number. Subsequent frames carry one or more application messages (for instance Pillar BinaryGateway order entry messages), each length-prefixed and typed so that a single TCP read can deliver a batch of messages to the application. The session layer provides acknowledged delivery, gap detection on inbound sequence numbers, and resumable recovery after disconnects.

Heartbeat frames are exchanged in both directions during idle periods and function as the liveness signal; a missed heartbeat triggers a disconnect. Logout messages cleanly terminate a session and flush any pending application traffic. On reconnect, clients specify the last acknowledged sequence number so the gateway can replay any messages that were sent but not acknowledged, providing at-least-once delivery semantics without duplicating processed messages.

### Transport

CommonClient operates over TCP providing reliable ordered delivery between an authorized client and the Pillar gateway. Every frame carries a little-endian packet header containing the packet length, message count, and sequence metadata, followed by a sequence of length-prefixed Pillar application messages.

### Key Characteristics

- **TCP session layer** - Reliable ordered delivery with framed Pillar application messages over TCP
- **Cross-market reuse** - Single session spec shared across NYSE equities, American, Arca, National, Texas, and options markets
- **Logon and authentication** - Session establishment with credentials and negotiated sequence number
- **Little-endian header** - Pillar uses little-endian byte ordering for packet header numeric fields
- **Batched messages** - Multiple application messages per TCP frame with per-message length prefixes
- **Heartbeats** - Bidirectional heartbeat frames detect dead connections during idle periods
- **Resumable recovery** - Clients reconnect specifying last acknowledged sequence number to replay missed messages
- **Shared order entry envelope** - Serves as the framing layer beneath Pillar BinaryGateway across every Pillar market

