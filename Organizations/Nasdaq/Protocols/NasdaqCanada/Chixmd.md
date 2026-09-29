## NasdaqCanada Chixmd: Nasdaq Canada Tcp Order And Trade Feed

Vendor level Tcp feed of the orders and trades on the Nasdaq Canada CXC, CX2 and CXD books.

### Overview

CHIXMD is the Tcp market data feed of Nasdaq Canada, inherited from Chi-X Canada. It carries the same order, execution, cancel, trade, broken trade, system event and stock status messages as the CHIXMMD multicast feed, in printable ascii with fixed width fields and long form variants for large sizes and prices.

The session layer is a simple SoupTcp style protocol. The sequence numbers are implied: the client counts the sequenced messages it has received and logs in with the next one it expects in order to recover after a disconnect.

### Transport

Tcp session of line feed terminated ascii packets: login, heartbeats and logout, and sequenced data packets with implied sequence numbers that can be replayed from any point of the day.

### Key Characteristics

- **Order by order** - Every displayed order published individually
- **Ascii messages** - Fixed width printable ascii fields with long form variants
- **Implied sequence numbers** - Recovery by logging in with the next expected sequence

