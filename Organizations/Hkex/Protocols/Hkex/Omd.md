## Omd: Hkex Orion Multicast Market Data

Binary multicast market data feed publishing real-time order book, trade, and reference data for securities and derivatives traded on the Hong Kong Exchanges and Clearing Orion platform.

### Overview

Orion Market Data (Omd) is the next-generation market data platform at the Hong Kong Exchanges and Clearing (Hkex), replacing legacy feeds with a unified binary multicast product across both securities and derivatives markets. The feed delivers the full order book, trade events, auction prices, reference data, and session state for every instrument listed on the Hkex trading platforms.

The protocol is distributed over Ip multicast with redundant A and B channels for resilience and uses compact fixed-width binary messages for low-latency processing. Complementary Tcp refresh and retransmission services provide book snapshots and replay of missed multicast messages, giving subscribers a complete reliability path for mid-day startup and gap recovery.

### Transport

Udp multicast for real-time delivery of the Orion market data stream, with primary and secondary multicast channels for redundancy and per-packet sequence numbers for gap detection. Tcp for the Orion refresh and retransmission services used by subscribers to recover missed multicast messages and initialise book state from snapshots.

### Key Characteristics

- **Orion platform** - Unified Hkex market data across securities and derivatives
- **Full order book** - Depth of book reconstruction from order events
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Refresh service** - Tcp book snapshots for mid-day initialisation
- **Retransmission** - Tcp replay of messages missed on the multicast feed
- **Binary encoded** - Fixed-width compact binary messages for low latency
- **Cash and derivatives** - Securities and derivatives on the same Orion backbone
- **Reference data** - Instrument definitions integrated with the feed

