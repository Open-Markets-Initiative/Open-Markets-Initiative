## Pillar: NYSE Pillar Trading Platform

Proprietary integrated trading technology platform developed by NYSE Group (Intercontinental Exchange) providing a unified binary protocol for order entry and market data across all NYSE equities and options exchanges.

### Overview

NYSE Pillar is an integrated trading technology platform designed to unify access to all NYSE Group markets under a single consistent architecture. The Pillar Binary Gateway provides a standardized protocol for member firms to submit orders and receive execution reports across NYSE, NYSE Arca, NYSE American, NYSE National, and NYSE Chicago. By consolidating previously disparate trading systems, Pillar reduces complexity for participants while enhancing performance and resiliency.

Pillar replaced multiple legacy systems that had evolved independently across the NYSE family of exchanges. For market data, the XDP (Exchange Data Publisher) feeds were migrated to Pillar proprietary data feeds, while for order entry, legacy gateways such as CCG and UTPDirect were superseded by the Pillar Gateway. The Pillar market data architecture includes the Integrated Feed, which provides a comprehensive order-by-order view of market events including depth of book, trades, order imbalances, and security status messages.

Market data feeds are distributed across multiple multicast channels with data partitioned for capacity management. The Pillar Gateway correlates order entry and market data through shared identifiers, with gateway OrderIDs mapping directly to OrderIDs in the market data feeds.

### Transport

The Pillar Binary Gateway operates over TCP for order entry and session management. For market data, Pillar uses UDP multicast with a dual-feed architecture where each channel provides two redundant multicast groups (Line A and Line B) for subscriber arbitration. Dedicated TCP-based request servers provide refresh and retransmission services for gap recovery and market state snapshots.

### Key Characteristics

- **Unified platform** - Single protocol for order entry across all NYSE Group equities and options markets
- **Binary encoding** - Fixed-length binary message format optimized for low-latency parsing
- **Dual-feed redundancy** - Market data delivered on two parallel multicast lines per channel for reliability
- **Order-by-order market data** - Integrated Feed provides full depth of book reconstruction capability
- **Correlated identifiers** - Gateway OrderIDs and DealIDs map directly to market data feed fields
- **Risk controls** - Built-in pre-trade risk management including price collars, order size limits, and kill switches
- **Multi-asset support** - Supports equities, options, and complex multi-leg options orders
