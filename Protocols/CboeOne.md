## CboeOne: Cboe One consolidated equities feed protocol

Binary Cboe One protocol of the Cboe One Equities Feed, which delivers consolidated quote, trade and Aggregated Depth At Price (ADAP) information for the Cboe U.S. equities exchanges via TCP/IP and UDP: Clear Quote, Symbol Summary, Best Quote Update, Market Status, ADAP, RPI, Trade, Trade Break, Trading Status, Opening/Closing Price and End of Day Summary messages.

### Overview

Cboe One consolidates the books of the Cboe U.S. equities exchanges (BZX, BYX, EDGX and EDGA) into one feed built from their PITCH services. It shares PITCH's Sequenced Unit Header framing and its Gap Request and Gap Response messages are identical to the Multicast PITCH ones, but the specification names it the Cboe One protocol.

Alphanumeric fields are left justified ASCII, space padded on the right; binary fields are unsigned and little endian; Binary 4.4 and Binary 8.4 prices carry 4 implied decimal places.

### Transport

UDP multicast from the Cboe One Feed Server: messages combined into frames counted by the Cboe Sequenced Unit Header, with the Cboe One Gap Request Proxy and Gap Server retransmitting missed packets. TCP/IP session to the Cboe One Feed Server carrying the same messages.

### Key Characteristics

- **Consolidated** - One feed across the Cboe U.S. equities exchanges
- **Little endian binary** - Unsigned little endian binary fields and implied decimal prices
- **Sequenced Unit Header** - The Cboe framing shared with PITCH

