## LynxAts Multicast Level2: Lynx Multicast Level 2

The Lynx ATS Level 2 Itch message set publishing the add, execute, replace, cancel and delete events that let a subscriber reconstruct the displayed book, alongside non-displayed Trade messages, trade busts and amendments, symbol directory and trading action messages, and the session lifecycle. Delivered over the Tradelogiq Quote Transfer Protocol, the multicast layer the specification names MoldUDP64, on two identically sequenced feeds A and B that subscribers arbitrate between. Lynx ATS carries a Midpoint Book alongside the displayed book, so the Trade message's Midpoint Book Trade indicator marks midpoint executions, and an Order Replace carrying a price change need not generate a new Order Reference Number even where priority was affected. Cross trades are not accepted on Lynx ATS.

### Overview

Tradelogiq Itch 5.0 is the outbound protocol of the Omega ATS and Lynx ATS data feeds. The Level 2 feed carries full order depth: the add, execute, replace, cancel and delete events that let a subscriber reconstruct the displayed book, alongside non-displayed Trade messages, trade busts and amendments, symbol directory and trading action messages, and the session lifecycle.

Every message is fixed length and begins with a one byte message type that the framing layer carries. Instruments are identified by a two byte Instrument ID that the Stock Directory and Extended Stock Directory messages map to symbols at the start of day. Integers are unsigned big endian, prices are integers carrying six whole digits and four decimal digits, and times are nanoseconds since midnight UTC recorded to microsecond precision.

Lynx ATS carries a Midpoint Book alongside the displayed book, so the Trade message's Midpoint Book Trade indicator marks midpoint executions, and an Order Replace carrying a price change need not generate a new Order Reference Number even where priority was affected. Cross trades are not accepted on Lynx ATS.

### Transport

Udp multicast via the Qtp downstream packet, carrying a session, the sequence number of the first message in the packet and a message count for gap detection; retransmission of up to ten prior minutes is available by unicast Request Packet to the Retransmission server.

### Key Characteristics

- **Level 2 market data** - the add, execute, replace, cancel and delete events that let a subscriber reconstruct the
- **Qtp multicast** - Packaged over the Tradelogiq Quote Transfer Protocol, a MoldUDP64 framing
- **Itch encoded** - Fixed length Itch 5.0 binary messages
- **Instrument identifiers** - Two byte Instrument ID mapped to symbols by the start of day directory
- **Dual feeds** - Two identically sequenced multicast feeds A and B for arbitration

