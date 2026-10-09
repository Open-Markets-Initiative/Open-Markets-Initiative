## OmegaAts Tcp Level1: Omega Tcp Level 1

The Omega ATS Level 1 Itch message set publishing a Quote message carrying the best bid and ask with their sizes, Trade Report, Trade Bust and Trade Correction messages, symbol directory and stock status messages, and the session lifecycle. Delivered over a point to point SoupTCPBinary session, each Sequenced Data Packet carrying exactly one Itch message with its sequence number implied. Omega ATS is the only Tradelogiq book that accepts intentional crosses, so the Cross Trade message appears on this feed and the Trade message's Midpoint Book Trade indicator is never set.

### Overview

Tradelogiq Itch 5.0 is the outbound protocol of the Omega ATS and Lynx ATS data feeds. The Level 1 feed carries top of book: a Quote message carrying the best bid and ask with their sizes, Trade Report, Trade Bust and Trade Correction messages, symbol directory and stock status messages, and the session lifecycle.

Every message is fixed length and begins with a one byte message type that the framing layer carries. Messages are keyed by the ten byte stock symbol rather than by Instrument ID, and prices are eight bytes rather than four. Integers are unsigned big endian, prices are integers carrying six whole digits and four decimal digits, and times are nanoseconds since midnight UTC recorded to microsecond precision.

Omega ATS is the only Tradelogiq book that accepts intentional crosses, so the Cross Trade message appears on this feed and the Trade message's Midpoint Book Trade indicator is never set.

### Transport

SoupTCPBinary v1.03 session, a two byte packet length and one byte packet type framing each logical packet, with login, logout and bidirectional heartbeats and guaranteed in order delivery of every sequenced message across socket failures.

### Key Characteristics

- **Level 1 market data** - a Quote message carrying the best bid and ask with their sizes, Trade Report, Trade Bust and
- **SoupTcp Binary session** - Point to point Tcp with login, logout and heartbeats
- **Itch encoded** - Fixed length Itch 5.0 binary messages
- **Symbol keyed** - Ten byte stock symbol carried on every message
- **Implied sequencing** - One message per Sequenced Data Packet, the sequence counted locally

