## Twime: TWIME

Binary order entry encoding of the Moscow Exchange derivatives market, carrying orders, cancels, replaces, mass cancels and their execution reports between a trading application and the TwimeGate gateway. The presentation layer is Simple Binary Encoding and the session layer follows FIXP, over a plain Tcp connection. Little-endian throughout, with a machine-readable message schema published alongside the specification.

### Overview

Every message is preceded by the eight byte Sbe message header giving the body length, the template id that selects the message, the schema id and the schema version. The schema declares no repeating groups and no variable length data, so the header's block length alone sizes every message.

The session layer binds a session to the Tcp connection with Establish, answered by EstablishmentAck or EstablishmentReject, and ends it with Terminate from each side. Sequence serves as the heartbeat in both directions. Only application messages from TwimeGate are numbered, starting from the NextSeqNo of EstablishmentAck, and a RetransmitRequest recovers missed ones.

Prices are the Decimal5 composite, a signed sixty-four bit mantissa with a constant exponent of minus five held in the schema, not on the wire. Timestamps are nanoseconds since the Unix epoch in UTC.

### Transport

A Tcp connection to TwimeGate carries one session in both directions. Each message is an eight byte Sbe header followed by its body, with no other framing, so several messages may share a segment and one message may span two.

### Key Characteristics

- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **FIXP session layer** - Establish, Terminate, Sequence heartbeats and retransmission follow the FIXP standard
- **Machine-readable schema** - The wire layout is published as an Sbe message schema, not only as a document
- **Composite prices** - A signed mantissa with a constant exponent of minus five held in the schema
- **Unix nanosecond clocks** - Every timestamp is nanoseconds since the Unix epoch in Utc

