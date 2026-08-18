## Index Product3: Koscom Market Data Service Realtime Index Product 3 product feed

Koscom-to-subscriber realtime market data output feed for the Index Product 3 subscription product of the Market Data Service (MDCS), publishing KRX market activity as Exture ASCII fixed-width records over UDP multicast with two-level TR-CODE dispatch.

### Transport

UDP multicast for real-time delivery of Exture ASCII fixed-width records, one message per datagram, framed by a 2-byte Data Category + 3-byte Information Category TR-CODE prefix and a 0xFF end-of-text sentinel, offered across line-speed tiers (100M, 45M, 12M, 8M, 512K). TCP retransmission service for gap recovery; subscribers detect gaps via Data Category-specific sequencing and request replay from the retransmission endpoint.

### Key Characteristics

- **Index Product 3 product feed** - MDCS Realtime Index Product 3 subscription product of the Koscom market data output feed
- **Exture ASCII wire format** - Fixed-width printable ASCII records with two-level TR-CODE dispatch and 0xFF end-of-text sentinel
- **UDP multicast delivery** - One message per UDP datagram over multicast for real-time low-latency distribution
- **TCP retransmission recovery** - Companion TCP retransmission service for gap recovery when subscribers detect missed messages

