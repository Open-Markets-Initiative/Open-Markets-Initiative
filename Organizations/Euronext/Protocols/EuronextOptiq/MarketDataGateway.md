## EuronextOptiq Market Data Gateway: Euronext Optiq Sbe Market Data

Sbe-encoded multicast market data protocol for the Euronext Optiq trading platform publishing order, trade, and reference data for cash and derivatives markets.

### Overview

The Optiq Market Data Gateway (Mdg) is the market data distribution channel for the Euronext Optiq trading platform. It delivers real-time order book events, trade messages, session and trading status updates, and instrument reference data for every Euronext cash and derivatives market running on Optiq, enabling subscribers to reconstruct the full order book and trade stream.

Messages use Simple Binary Encoding (Sbe) with compact fixed-width fields for low-latency decoding, distributed over Ip multicast with A/B channel redundancy. Tcp-based snapshot and retransmission services are available for subscribers that join mid-day, miss multicast packets, or need to resynchronize after a gap, providing the full reliability path expected of a primary market data feed.

### Transport

Udp multicast for real-time delivery of Sbe-encoded order book, trade, and reference data messages with per-packet sequence numbers for gap detection. Tcp for the Optiq snapshot and retransmission services used by subscribers to recover missed multicast messages or initialise book state.

### Key Characteristics

- **Optiq platform** - Native market data gateway for the Euronext Optiq trading system
- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low-latency parsing
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Full order book** - Incremental order events for complete depth reconstruction
- **Snapshot recovery** - Tcp book snapshots for mid-day initialisation
- **Retransmission** - Tcp service for recovery of missed multicast messages
- **Cash and derivatives** - Unified feed across Euronext Optiq asset classes
- **Reference data** - Instrument definitions integrated with the feed

