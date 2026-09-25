## Atr: Automated Trade Reporting

Proprietary text protocol developed by TMX Group and licensed to several exchanges for reporting trades, allocations and give-ups on the Sola trading platform.

### Overview

ATR (Automated Trade Reporting) carries the post-trade side of the Sola trading platform: the trades the matching engine executes, the allocations that apportion them and the give-ups that pass them to another firm. Where SAIL is how an order reaches the engine, ATR is how the resulting trade reaches the firm that must clear it.

Every ATR message is a fixed extent rather than a length-prefixed one, opened by a 28 byte header naming the source, the destination and the message type, and closed by an end of text. Each field is written as text in a fixed column, numeric fields right justified and zero filled, alphabetic fields left justified and blank filled.

### Transport

ATR operates over TCP, providing reliable ordered delivery of trade reports between the Sola matching engine and clearing participants. The protocol includes signon, circuit assurance and sequencing mechanisms for session management, and a restart request for recovering a gap.

### Key Characteristics

- **Post trade reporting** - Carries trades, allocations and give-ups rather than orders
- **Bidirectional** - The server reports trades, the participant allocates and gives up
- **Fixed extent messages** - Each message states its own byte count, with no length on the wire
- **Text in fixed columns** - Every field is written as text, justified and filled by its data type
- **Sola platform native** - Designed specifically for the Sola matching engine architecture

