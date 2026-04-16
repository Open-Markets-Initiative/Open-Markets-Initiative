## NtxEquities Total View: Nasdaq TX Full Depth Of Book Market Data

Full depth of book Itch-based market data feed publishing order-by-order events for equities traded on Nasdaq Texas Equities.

### Overview

TotalView is the full depth of book market data feed for Nasdaq Texas Equities, publishing order-by-order events using the Nasdaq Itch binary protocol. The feed delivers order add, modify, execute, and delete messages enabling subscribers to reconstruct the complete limit order book for every listed equity instrument.

Messages are distributed over Ip multicast using the MoldUdp64 framing, with a companion SoupBinTcp glimpse snapshot service for subscribers joining mid-day and a retransmission service for gap recovery. Trade messages, reference data, trading status, and Reg SHO events are carried inline with the order events.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, execute, and delete events
- **Nasdaq Itch** - Industry-standard Itch binary message format
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Glimpse snapshot** - Tcp snapshot service for mid-day initialisation
- **Retransmission** - Tcp service for recovery of missed multicast messages
- **Reg SHO** - Short sale restriction status updates
- **Reference data** - Stock directory and trading action messages

