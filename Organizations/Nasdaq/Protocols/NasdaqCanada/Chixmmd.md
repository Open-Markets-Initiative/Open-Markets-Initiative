## NasdaqCanada Chixmmd: Nasdaq Canada Multicast Order And Trade Feed

Real time multicast feed of the orders and trades on the Nasdaq Canada CXC, CX2 and CXD books, with its Glimpse snapshot service.

### Overview

CHIXMMD is the multicast market data feed of Nasdaq Canada, inherited from Chi-X Canada. It publishes every displayed order added to, executed on or cancelled from the CXC and CX2 books, trades against hidden quantity on all three books, broken trades, system events and the stock status of each symbol. Messages are printable ascii with fixed width fields, and long form variants carry sizes and prices too large for the standard layout.

Each book is published on its own multicast channel, duplicated on two streams at each site. Missed messages are recovered from the Multicast Message Recovery Service, and a subscriber joining mid session builds the book from Nasdaq Canada Glimpse, which replays the stock status and displayed orders in the same message formats.

### Transport

Udp multicast, one channel per book, each packet a binary sequence number and message count followed by length prefixed ascii messages; a packet with a count of zero is a heartbeat carrying the session. Tcp to the Multicast Message Recovery Service, which replays missed messages over the CHIXMD session protocol, and to the Glimpse snapshot service over SoupTcp.

### Key Characteristics

- **Order by order** - Every displayed order published individually
- **Ascii messages** - Fixed width printable ascii fields with long form variants
- **Three books** - CXC, CX2 and CXD on separate multicast channels
- **Recovery and snapshot** - Tcp message recovery service and Glimpse snapshot

