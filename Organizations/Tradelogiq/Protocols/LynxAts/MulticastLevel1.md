## LynxAts Multicast Level1: Lynx Multicast Level 1

The Lynx ATS Level 1 Itch message set publishing a Quote message carrying the best bid and ask with their sizes, Trade Report, Trade Bust and Trade Correction messages, symbol directory and stock status messages, and the session lifecycle. Delivered over the Tradelogiq Quote Transfer Protocol, the multicast layer the specification names MoldUDP64, on two identically sequenced feeds A and B that subscribers arbitrate between. Lynx ATS carries a Midpoint Book alongside the displayed book, so the Trade message's Midpoint Book Trade indicator marks midpoint executions, and an Order Replace carrying a price change need not generate a new Order Reference Number even where priority was affected. Cross trades are not accepted on Lynx ATS.

### Overview

Tradelogiq Itch 5.0 is the outbound protocol of the Omega ATS and Lynx ATS data feeds. The Level 1 feed carries top of book: a Quote message carrying the best bid and ask with their sizes, Trade Report, Trade Bust and Trade Correction messages, symbol directory and stock status messages, and the session lifecycle.

Every message is fixed length and begins with a one byte message type that the framing layer carries. Messages are keyed by the ten byte stock symbol rather than by Instrument ID, and prices are eight bytes rather than four. Integers are unsigned big endian, prices are integers carrying six whole digits and four decimal digits, and times are nanoseconds since midnight UTC recorded to microsecond precision.

Lynx ATS carries a Midpoint Book alongside the displayed book, so the Trade message's Midpoint Book Trade indicator marks midpoint executions, and an Order Replace carrying a price change need not generate a new Order Reference Number even where priority was affected. Cross trades are not accepted on Lynx ATS.

### Transport

Udp multicast via the Qtp downstream packet, carrying a session, the sequence number of the first message in the packet and a message count for gap detection; retransmission of up to ten prior minutes is available by unicast Request Packet to the Retransmission server.

### Key Characteristics

- **Level 1 market data** - a Quote message carrying the best bid and ask with their sizes, Trade Report, Trade Bust and
- **Qtp multicast** - Packaged over the Tradelogiq Quote Transfer Protocol, a MoldUDP64 framing
- **Itch encoded** - Fixed length Itch 5.0 binary messages
- **Symbol keyed** - Ten byte stock symbol carried on every message
- **Dual feeds** - Two identically sequenced multicast feeds A and B for arbitration

