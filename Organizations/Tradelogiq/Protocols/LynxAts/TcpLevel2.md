## LynxAts Tcp Level2: Lynx Tcp Level 2

The Lynx ATS Level 2 Itch message set publishing the add, execute, replace, cancel and delete events that let a subscriber reconstruct the displayed book, alongside non-displayed Trade messages, trade busts and amendments, symbol directory and trading action messages, and the session lifecycle. Delivered over a point to point SoupTCPBinary session, each Sequenced Data Packet carrying exactly one Itch message with its sequence number implied. Lynx ATS carries a Midpoint Book alongside the displayed book, so the Trade message's Midpoint Book Trade indicator marks midpoint executions, and an Order Replace carrying a price change need not generate a new Order Reference Number even where priority was affected. Cross trades are not accepted on Lynx ATS.

### Overview

Tradelogiq Itch 5.0 is the outbound protocol of the Omega ATS and Lynx ATS data feeds. The Level 2 feed carries full order depth: the add, execute, replace, cancel and delete events that let a subscriber reconstruct the displayed book, alongside non-displayed Trade messages, trade busts and amendments, symbol directory and trading action messages, and the session lifecycle.

Every message is fixed length and begins with a one byte message type that the framing layer carries. Instruments are identified by a two byte Instrument ID that the Stock Directory and Extended Stock Directory messages map to symbols at the start of day. Integers are unsigned big endian, prices are integers carrying six whole digits and four decimal digits, and times are nanoseconds since midnight UTC recorded to microsecond precision.

Lynx ATS carries a Midpoint Book alongside the displayed book, so the Trade message's Midpoint Book Trade indicator marks midpoint executions, and an Order Replace carrying a price change need not generate a new Order Reference Number even where priority was affected. Cross trades are not accepted on Lynx ATS.

### Transport

SoupTCPBinary v1.03 session, a two byte packet length and one byte packet type framing each logical packet, with login, logout and bidirectional heartbeats and guaranteed in order delivery of every sequenced message across socket failures.

### Key Characteristics

- **Level 2 market data** - the add, execute, replace, cancel and delete events that let a subscriber reconstruct the
- **SoupTcp Binary session** - Point to point Tcp with login, logout and heartbeats
- **Itch encoded** - Fixed length Itch 5.0 binary messages
- **Instrument identifiers** - Two byte Instrument ID mapped to symbols by the start of day directory
- **Implied sequencing** - One message per Sequenced Data Packet, the sequence counted locally

