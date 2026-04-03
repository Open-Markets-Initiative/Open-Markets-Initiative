## PsxEquities TotalView: Nasdaq Psx Full Depth Of Book

Itch market data feed providing full depth of book visibility for all displayed orders on the Nasdaq Psx exchange.

### Overview

TotalView is the primary Nasdaq Psx depth of book feed, delivering every displayed order and quote update for all Psx-listed securities. The feed provides order-by-order granularity including add, modify, delete, and execute messages with nanosecond timestamps.

The feed uses Itch binary encoding and includes system event, stock directory, trading action, and regulatory reference data messages. TotalView enables full limit order book reconstruction for all Psx displayed interest.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Full depth of book** - Every displayed order at every price level
- **Order-by-order** - Individual order add, modify, delete, and execute messages
- **Nanosecond timestamps** - High-resolution event timing
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
