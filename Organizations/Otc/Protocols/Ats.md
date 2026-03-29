## Ats: Otc Alternative Trading System Feed

Multicast market data protocol providing real-time Ats trading information for Otc equity securities.

### Overview

The Otc Ats feed is a multicast market data protocol delivering real-time trading activity from alternative trading systems for over-the-counter equity securities. The protocol disseminates quote and trade information for Otc-listed equities, providing visibility into Ats venues that trade Otc securities.

The feed provides subscribers with Ats-specific market data including best bid and offer quotes, trade executions, and volume statistics for Otc equities. This enables market participants to monitor Ats liquidity and trading activity in the Otc equity market alongside traditional Otc Markets quotation data.

### Transport

Udp multicast with sequenced packets for efficient one-to-many delivery of Ats market data.

### Key Characteristics

- **Multicast delivery** - Udp multicast for efficient Ats data distribution
- **Otc equities** - Market data for over-the-counter equity securities
- **Ats coverage** - Trading activity from alternative trading systems
- **Quote and trade data** - Best bid/offer quotes and trade execution reports
- **Real-time feed** - Low-latency dissemination of Ats market activity
- **Sequence numbered** - Packets carry sequence numbers for gap detection
