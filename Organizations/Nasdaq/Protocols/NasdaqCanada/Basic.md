## NasdaqCanada Basic: Nasdaq Canada Level 1 Quotation And Trade Data

Level 1 Itch-based market data feed publishing the combined best bid and offer of the Nasdaq Canada CXC and CX2 books and every trade on CXC, CX2 and CXD.

### Overview

Nasdaq Basic Canada is a single Level 1 product covering all three Nasdaq Canada trading books. Its quotation message carries the combined best bid and offer of the lit CXC and CX2 books with the size attributed to each, and its trade messages report every transaction on CXC, CX2 and CXD with breaks and corrections.

Messages use the Nasdaq Itch binary format with eight byte prices of eight implied decimals and eight byte nanosecond timestamps past midnight Eastern Time, distributed over Ip multicast via MoldUdp64.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages.

### Key Characteristics

- **Combined top of book** - Best bid and offer across CXC and CX2 with per-book size
- **Three books** - Trades from CXC, CX2 and CXD
- **End of day summary** - Consolidated high, low, open, close and volume per symbol
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing

