## IseOptions Trade Combo Feed: Ise Trade Combo Feed

Trade feed publishing executed multi-leg combo strategy trades on the Nasdaq Ise Options Exchange.

### Overview

Trade feed publishing executed multi-leg combo strategy trades on the Nasdaq Ise Options Exchange

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Combo trade reports** - Multi-leg strategy executions
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Per-leg allocation** - Trade details with per-leg breakdown
- **Gap recovery** - SoupBinTcp based recovery service

