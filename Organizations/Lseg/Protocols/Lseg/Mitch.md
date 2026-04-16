## Mitch: Lseg Millennium Exchange Order Book Market Data

Millennium Itch-based binary market data feed publishing order by order events and trade messages for securities traded on the London Stock Exchange Millennium Exchange platform.

### Overview

Mitch is the Millennium Itch market data protocol used by the London Stock Exchange Group (Lseg) to distribute real-time order book and trade data for securities traded on the Millennium Exchange platform. The feed delivers order add, modify, execute, and delete events along with trade messages, enabling subscribers to reconstruct the full order book for every listed instrument.

Messages are delivered as fixed-width binary messages over MoldUdp64 multicast, with complementary Tcp replay and snapshot services for gap recovery and mid-day initialisation. The wire format is a Millennium variant of the Nasdaq Itch protocol tailored for the Lseg product set and trading conventions.

### Transport

Udp multicast carrying Mitch binary messages over MoldUdp64 framing for real-time delivery of order book and trade events with per-packet sequence numbers for gap detection. Tcp to the Millennium replay and snapshot services for recovery of messages missed on the multicast feed and initialisation of book state.

### Key Characteristics

- **Millennium Exchange** - Native market data for the Lseg Millennium platform
- **Itch derived** - Millennium variant of the Nasdaq Itch protocol family
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Order-by-order** - Add, modify, execute, and delete events for each order
- **Snapshot and replay** - Tcp recovery services for mid-day startup and gap fill
- **Binary encoded** - Fixed-width compact binary messages for low latency processing

