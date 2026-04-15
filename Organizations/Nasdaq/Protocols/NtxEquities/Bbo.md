## NtxEquities Bbo: Nasdaq TX Top Of Book Quotation Data

Top of book Itch-based market data feed publishing best bid and offer quotations for equities traded on Nasdaq Texas Equities.

### Overview

Bbo is the top of book market data feed for Nasdaq Texas Equities, publishing best bid and best offer updates for every listed equity instrument. It is a lightweight alternative to the full TotalView depth feed, providing current quotations without the overhead of order-by-order events.

Messages use the Nasdaq Itch binary format and are distributed over Ip multicast via MoldUdp64. A companion SoupBinTcp glimpse snapshot and retransmission service is available for gap recovery and mid-day initialisation.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Top of book** - Best bid and best offer for every listed instrument
- **Nasdaq Itch** - Industry-standard Itch binary message format
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Glimpse snapshot** - Tcp snapshot service for mid-day initialisation
- **Retransmission** - Tcp service for recovery of missed multicast messages
- **Lightweight** - Low bandwidth alternative to full depth of book

