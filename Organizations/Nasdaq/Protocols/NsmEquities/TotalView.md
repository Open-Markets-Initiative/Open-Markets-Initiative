## NsmEquities TotalView: Nasdaq Stock Market Full Depth Of Book

Itch market data feed providing full depth of book visibility for all displayed orders on the Nasdaq Stock Market.

### Overview

TotalView is the premier Nasdaq Stock Market data feed, delivering every displayed order and quote update for all Nsm-listed and Upa securities. The feed provides order-by-order granularity including add, modify, delete, and execute messages with nanosecond timestamps, enabling subscribers to reconstruct the complete limit order book at any point in time.

TotalView is the highest-bandwidth Itch feed on Nsm, carrying the full displayed order lifecycle from entry through execution or cancellation. It includes system event, stock directory, trading action, and regulatory messages alongside order and trade data.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Full depth of book** - Every displayed order at every price level
- **Order-by-order** - Individual order add, modify, delete, and execute messages
- **Nanosecond timestamps** - High-resolution event timing
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
