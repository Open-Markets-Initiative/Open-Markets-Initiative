## Snap: IEX Snapshot Recovery Protocol

Request-response snapshot protocol developed by IEX Exchange to accelerate late-start recovery on its market data feeds. A client authenticates with a Snapshot Request over TCP and receives a point-in-time snapshot of feed state as a stream of Snapshot Data messages, each wrapping one complete feed message with its IexTp header.

### Overview

Snap augments the IexTp gap-fill retransmission service with a separate snapshot protocol. Applications buffer the real-time multicast, connect to a Snap server, and issue a Snapshot Request carrying an authentication token plus the channel, session, and minimum sequence number observed on the feed. A successful response is a Snapshot Start message, a stream of Snapshot Data messages, and a Snapshot End message carrying the sequence number at which the snapshot was created.

Each Snapshot Data message wraps one complete feed message together with an IexTp header providing the original feed sequencing and timing information, so consumers can initialize their books from the snapshot and then apply buffered real-time updates with higher sequence numbers. Snap services exist for the Tops, Deep, and Deep Plus feeds, each with its own server addresses and specification.

### Transport

Length-framed binary messages over a TCP connection: a 2-byte little-endian message length counting the bytes after the field, a 1-byte ascii message type, then the message data. The protocol is strictly request-response with no unsolicited messages; idle connections may be disconnected by either side.

### Key Characteristics

- **Request response** - Client-initiated snapshot requests with no unsolicited messages
- **Length-framed Tcp** - Two-byte message length plus one-byte ascii message type framing
- **Point-in-time snapshot** - Feed state for all symbols at a single sequence number
- **Wrapped feed messages** - Snapshot Data messages carry complete feed messages with their IexTp headers
- **Authenticated** - Token-based authentication with daily request quotas
- **Per-feed services** - Separate Snap servers and specifications for Tops, Deep, and Deep Plus

