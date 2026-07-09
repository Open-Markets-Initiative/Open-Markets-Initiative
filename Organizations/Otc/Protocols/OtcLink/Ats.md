## OtcLink Ats: Otc Markets Alternative Trading System Data Feed

Market data feed publishing quotations, trade reports, and security status events for Otc securities traded on the Otc Markets alternative trading system.

### Overview

Otc Ats is the market data feed for the Otc Markets alternative trading system, providing subscribers with real-time quotations, trade reports, and security status information for securities trading in the Otc market. The feed covers the full Otc universe including Pink, Otcqb, and Otcqx tiers.

Messages are delivered as sequenced binary records over Ip multicast with a companion Tcp re-request service for gap recovery. The protocol supports quote update, trade report, administrative events such as trading halts, and reference data messages for each tradable security.

### Transport

Udp multicast for real-time delivery of sequenced binary quote and trade messages with per-packet sequence numbers for gap detection. Tcp for the re-request service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Otc market data** - Quotes and trades for Otc Markets securities
- **Multi-tier coverage** - Pink, Otcqb, and Otcqx tier securities
- **Multicast delivery** - Real-time Udp multicast distribution of quote events
- **Trade reports** - Last sale messages with price, size, and conditions
- **Security status** - Trading halt and status notifications for listed securities
- **Re-request service** - Tcp-based gap recovery for missed multicast messages
- **Binary encoded** - Fixed-width compact binary message format

