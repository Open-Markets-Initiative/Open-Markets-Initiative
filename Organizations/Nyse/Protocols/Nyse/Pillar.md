## Pillar: Nyse Pillar Unified Order Entry And Market Data

Binary trading platform interface covering order entry, execution, and market data for securities traded on Nyse Pillar venues including Nyse, Nyse Arca, Nyse American, Nyse Chicago, and Nyse National.

### Overview

Pillar is the unified trading platform of the New York Stock Exchange, providing consolidated order entry, execution, and market data services across the Nyse family of equities and options venues. It replaces the legacy matching engines and protocols with a single native binary interface built around a common session layer, message model, and reference data format.

The Pillar protocol family covers the full lifecycle of trading activity from order submission through execution reporting, drop copy, and market data dissemination. Order entry sessions run over Tcp with authentication and sequence tracking, while market data is distributed over Ip multicast with A and B channel redundancy and a companion retransmission service for gap recovery.

### Transport

Tcp for persistent authenticated Pillar sessions carrying order entry, execution report, and drop copy messages between member firms and the Nyse matching engine. Udp multicast for Pillar market data distribution, delivering real-time order book and trade events over A and B multicast channels with per-packet sequence numbers.

### Key Characteristics

- **Unified trading platform** - Common interface across Nyse equities and options venues
- **Order entry** - Full order lifecycle over authenticated Tcp sessions
- **Market data** - Real-time multicast distribution with A and B channel redundancy
- **Drop copy** - Read-only side channel for back office and risk systems
- **Multi-venue** - Nyse, Nyse Arca, Nyse American, Nyse Chicago, and Nyse National
- **Binary encoded** - Fixed-width Pillar-native message format for low latency
- **Common reference data** - Unified security definitions across all Pillar markets

