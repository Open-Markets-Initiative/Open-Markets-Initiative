## BxEquities LastSale: Nasdaq Bx Last Sale

Itch market data feed providing trade execution reports for Nasdaq Bx securities.

### Overview

LastSale delivers real-time trade execution reports for all Bx-listed securities, including trade price, size, and sale condition information. The feed provides post-trade transparency for all matched executions on the Bx exchange.

The feed uses Itch binary encoding and includes the standard Bx reference data messages. Trade reports carry execution details including match number and sale conditions for regulatory reporting.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Trade reports** - Real-time execution price, size, and sale conditions
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
- **Consolidated trade identifiers** - Match numbers for regulatory and audit purposes
