## OmegaAts Multicast Level2: Omega Multicast Level 2

Order-by-order full depth market data feed for Omega ATS, publishing the add, execute, replace, cancel and delete events that let a subscriber reconstruct the displayed book, alongside non-displayed Trade messages, intentional Cross Trade messages, trade busts and amendments, symbol directory and trading action messages, and the session lifecycle. Delivered over the Tradelogiq Quote Transfer Protocol, the multicast layer the specification names MoldUDP64, on two identically sequenced feeds A and B that subscribers arbitrate between.

### Overview

Tradelogiq Itch 5.0 is the outbound protocol of the Omega ATS and Lynx ATS multicast data feeds. The Level 2 feed carries the full order depth: order messages tracking the life of each customer order, execution messages reflecting regular executions, executions of non-displayed orders and intentional crosses, and administrative messages carrying session events, symbol state changes and the symbol directory.

Every message is fixed length and begins with a one byte message type that the Qtp message block header carries. Instruments are identified by a two byte Instrument ID that the Stock Directory and Extended Stock Directory messages map to symbols at the start of day. Integers are unsigned big endian, prices are integers carrying six whole digits and four decimal digits, and times are nanoseconds since midnight UTC recorded to microsecond precision.

Cross Trade messages are accepted on Omega ATS only. The Trade message carries a Midpoint Book Trade indicator that is set for Lynx ATS midpoint executions, so an Omega subscriber sees it unset.

### Transport

Udp multicast via the Qtp downstream packet, carrying a session, the sequence number of the first message in the packet and a message count for gap detection; retransmission of up to ten prior minutes is available by unicast Request Packet to the Retransmission server.

### Key Characteristics

- **Full order depth** - Order-by-order add, execute, replace, cancel and delete events
- **Qtp multicast** - Packaged over the Tradelogiq Quote Transfer Protocol, a MoldUDP64 framing
- **Itch encoded** - Fixed length Itch 5.0 binary messages
- **Instrument identifiers** - Two byte Instrument ID mapped to symbols by the start of day directory
- **Intentional crosses** - Derivatives, internal, intentional and net asset value crosses, Omega only
- **Trade corrections** - Trade bust and trade amend messages following a CIRO ruling or voluntary bust
- **Dual feeds** - Two identically sequenced multicast feeds A and B for arbitration

