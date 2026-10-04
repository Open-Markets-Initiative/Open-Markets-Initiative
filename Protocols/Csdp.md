## Csdp: Cboe Summary Depth feed protocol

Binary Cboe Summary Depth protocol of the Cboe U.S. Equities Summary Depth Feed, which delivers quote, trade and Aggregated Depth At Price (ADAP) information for the respective Cboe book via TCP/IP and UDP: Clear Quote, Market Status, ADAP, RPI, Trade, Trade Break and Trading Status messages.

### Overview

Summary Depth summarises one Cboe U.S. equities book (BZX, BYX, EDGX or EDGA) from that exchange's PITCH service. It shares PITCH's Sequenced Unit Header framing and its Gap Request and Gap Response messages are identical to the Multicast PITCH ones, but the specification names it the Cboe Summary Depth protocol.

Alphanumeric fields are left justified ASCII, space padded on the right; binary fields are unsigned and little endian; Binary 4.4 and Binary 8.4 prices carry 4 implied decimal places.

### Transport

UDP multicast from the Cboe Summary Depth Feed Server: messages combined into frames counted by the Cboe Sequenced Unit Header, with the Cboe Summary Depth Gap Request Proxy and Gap Server retransmitting missed packets. TCP/IP session to the Cboe Summary Depth Feed Server carrying the same messages.

### Key Characteristics

- **Aggregated depth** - Quote, trade and aggregated depth at price for one Cboe book
- **Little endian binary** - Unsigned little endian binary fields and implied decimal prices
- **Sequenced Unit Header** - The Cboe framing shared with PITCH

