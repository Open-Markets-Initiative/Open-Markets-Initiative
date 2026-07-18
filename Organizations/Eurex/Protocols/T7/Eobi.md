## T7 Eobi: Eurex T7 Order Book Market Data

Binary market data feed publishing the full unnetted order book and trade events for derivatives traded on the Eurex T7 platform via Ip multicast.

### Overview

Eobi is the Eurex Enhanced Order Book Interface, the market data feed for the Eurex T7 platform. It publishes the complete unnetted order book including every visible order event, enabling subscribers to reconstruct the full depth of book for every listed instrument. The feed also carries trade messages, auction events, and reference data.

Messages are disseminated over Ip multicast as a sequenced stream with per-packet sequence numbers for gap detection. Complementary Tcp services provide book snapshot recovery for subscribers joining mid-day and retransmission of messages lost on the multicast feed, covering the full reliability path for the T7 market data product.

### Transport

Udp multicast for real-time delivery of incremental order book updates, trade messages, and reference data with per-packet sequence numbers for gap detection. Tcp for the T7 retransmission and snapshot services used by subscribers to recover missed multicast messages or initialise book state.

### Key Characteristics

- **Full unnetted book** - Every visible order event for complete depth of book reconstruction
- **T7 platform** - Native market data interface for the Eurex T7 trading system
- **Multicast delivery** - Real-time Udp multicast distribution of the market data stream
- **Snapshot service** - Tcp book snapshots for mid-day initialisation
- **Retransmission** - Tcp service for recovery of missed multicast messages
- **Trade messages** - Executed trade events published alongside the order book stream
- **Reference data** - Instrument definitions integrated with the feed
- **Derivatives** - Futures and options listed on Eurex

