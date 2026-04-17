## NtxEquities Glimpse: Nasdaq Ntx Equities Snapshot Retransmission Service

Tcp snapshot and retransmission service providing a point in time view of the order book for recovery and mid-day initialisation for Ntx Equities.

### Overview

Glimpse is the Nasdaq snapshot and retransmission service, providing a point in time order book view over SoupBinTcp for recovery of missed multicast messages and mid-day initialisation of subscriber state.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Snapshot delivery** - Point in time order book state for Ntx Equities
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Ntx Equities** - Coverage of Nasdaq Ntx Equities listed instruments

