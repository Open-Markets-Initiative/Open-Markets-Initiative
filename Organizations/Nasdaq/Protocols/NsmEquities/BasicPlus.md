## NsmEquities Basic Plus: Nasdaq Consolidated Best Bid And Offer Quotation Data

Top of book Itch-based market data feed publishing the consolidated best bid and offer across the Nasdaq, Nasdaq Texas and Nasdaq PSX execution systems.

### Overview

Basic Plus publishes the consolidated best bid and offer across the three Nasdaq operated equity exchanges, naming for each side the exchange or exchanges at the best price, together with the retail price interest indicator and the administrative messages a display needs.

Messages use the Nasdaq Itch binary format with eight byte prices and nanosecond Unix epoch timestamps, and are distributed over Ip multicast via MoldUdp64 or over SoupBinTcp.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp, plain or compressed, for sequenced delivery of the same messages.

### Key Characteristics

- **Consolidated top of book** - Best bid and offer across Nasdaq, Nasdaq Texas and PSX
- **Exchange attribution** - Exchange indicator naming the markets at the best bid and offer
- **Nasdaq Itch** - Industry-standard Itch binary message format
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Epoch timestamps** - Eight byte nanoseconds since the Unix epoch, UTC

