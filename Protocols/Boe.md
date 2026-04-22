## Boe: Cboe Binary Order Entry

Proprietary binary order entry protocol developed by BATS Global Markets (now Cboe Global Markets) for low-latency order submission, modification, and cancellation across Cboe equities, options, futures, and international exchanges.

### Overview

Binary Order Entry (BOE) is Cboe's proprietary protocol for submitting and managing orders on its matching engines. While Cboe also supports FIX as an order entry protocol, BOE is a binary alternative designed for reduced message sizes and lower parsing latency, making it the preferred choice for latency-sensitive participants such as market makers and proprietary trading firms.

BOE has evolved through multiple major versions. The original BOE and BOE2 were widely deployed across BATS and later Cboe exchanges. BOE version 3 (BOEv3) is the current generation, introducing further improvements to support the unified Cboe Titanium platform architecture. BOEv3 has been rolled out across US equities, US options, the Cboe Futures Exchange (CFE), and international markets including Cboe Europe, Japan, Australia, and Canada.

The protocol employs a simple session-level design covering login, sequencing, replay of missed messages, heartbeats, and logout. Each BOE order handler process accepts a single TCP connection from a member firm, and order handlers connect to matching units via latency-equalized connections ensuring fair access to the matching engine.

### Transport

BOE operates over TCP. Each member firm establishes a persistent TCP connection to a BOE order handler providing reliable ordered delivery in both directions. The session begins with a Login Request/Response handshake and is maintained through periodic heartbeat messages. Every message starts with a two-byte Start of Message marker (0xBABA) followed by a fixed 10-byte message header. All binary fields use little-endian byte ordering.

### Key Characteristics

- **Binary encoding** - All fields are binary with little-endian byte ordering, reducing message size and parsing overhead
- **Start of Message marker** - Every message begins with the bytes 0xBA 0xBA for reliable message framing
- **Single connection per handler** - Each BOE order handler accepts one TCP connection per member firm
- **IP-based access control** - Connection attempts from unknown source IP ranges are blocked
- **Latency-equalized matching** - Order handler connections to matching engines are latency equalized for fair access
- **Optional fields via bitfields** - Bitfield parameters indicate which optional fields are present, reducing message size
- **Multiple versions** - BOE, BOE2, and BOEv3 specifications coexist across different markets and migration timelines
- **Multi-asset support** - Separate specifications for equities, options, futures, and international markets

