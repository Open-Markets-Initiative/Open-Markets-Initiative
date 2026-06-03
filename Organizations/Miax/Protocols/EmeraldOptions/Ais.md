## EmeraldOptions Ais: Miax Emerald Options Administrative Information Subscriber Feed

Reference data and administrative feed publishing option series, complex strategy definitions, trading status, system state, and liquidity seeking event notifications for the Miax Emerald Exchange.

### Overview

Emerald Options Administrative Information Subscriber (Ais) is the reference data feed for the Miax Emerald Exchange, publishing the list of option series and complex strategies traded for the current session along with system state, trading status, and liquidity seeking event notifications. Subscribers use the feed to build and maintain their symbol and strategy lists and to react to system-level events.

The feed shares the Miax Express binary format used across all Miax sub-exchanges. Messages are distributed over Ip multicast with A and B channel redundancy, and subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and last value refresh recovery.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary administrative and reference data messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and last value refresh of messages missed on the multicast feed.

### Key Characteristics

- **Series and strategy reference** - Simple option series and complex strategy definitions published for the current session
- **Liquidity seeking events** - Simple and complex liquidity seeking event notifications for auctions and imbalances
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Last value refresh** - Intra-day recovery without a full day gap fill
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Trading status** - System event and instrument-level status notifications

