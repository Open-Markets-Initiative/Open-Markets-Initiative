## Simba: SIMBA

Low-latency market data encoding of the Moscow Exchange, carrying the full order log as FIX messages in Simple Binary Encoding. Published as paired A and B multicast streams on separate groups, with a looping snapshot stream for recovery and a Tcp replay service for the current trading session. Little-endian throughout, with a machine-readable message schema published alongside the specification.

### Overview

Messages are FIX messages encoded with Simple Binary Encoding version 1, taking their field names, types and structure from the FIX standard. Every message is preceded by an eight byte Sbe header giving the root block length, the template id that selects the message, the schema id and the schema version. Repeating groups carry their own two or three byte dimension header of a block length and an entry count.

Prices are Sbe composites of a signed sixty-four bit mantissa and a constant exponent, so the scale is carried by the schema rather than the wire: Decimal5 and Decimal5NULL state an exponent of minus five, Decimal2NULL minus two. The nullable forms signal absence with the maximum positive mantissa rather than with a separate flag.

Both the packet sending time and the transaction time are nanoseconds since the Unix epoch in UTC, which is unusual for a market data feed of this family and removes any need for a session date to interpret them.

A transaction too large for a single datagram is fragmented, and the packet header's message flags mark the pieces: LastFragment distinguishes a final or unfragmented packet, StartOfSnapshot and EndOfSnapshot bracket an instrument's snapshot, IncrementalPacket separates the two packet shapes, and PossDupFlag marks a full order book replayed as incremental packets.

### Transport

Udp multicast carries both the incremental and the snapshot streams, each duplicated as an A and a B group so a subscriber can arbitrate the two against packet loss. An incremental packet carries a market data packet header, an incremental packet header stating when matching began on the transaction, and one or more Sbe messages; a snapshot packet carries the market data packet header and exactly one Sbe message. A Tcp replay service recovers the current trading session. The client logs on and asks for a sequence range with a market data request; the gateway answers in snapshot packet framing with the same incremental messages it had multicast.

### Key Characteristics

- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Machine-readable schema** - The wire layout is published as an Sbe message schema, not only as a document
- **Full order log** - Order-by-order add, change and delete events with executions reported separately
- **Best prices first** - A transaction opens with the resulting best bid and offer before the order events
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration
- **Composite prices** - A signed mantissa with a constant exponent held in the schema, not on the wire
- **Unix nanosecond clocks** - Packet sending time and transaction time are both nanoseconds since the Unix epoch in Utc
- **Packet fragmentation flags** - A flags word marks fragment boundaries, snapshot boundaries and replayed books

