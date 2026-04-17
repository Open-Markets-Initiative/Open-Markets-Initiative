## AsxSecurities Ntp: Asx Ntp Itch Market Data

High-speed binary market data protocol publishing real-time reference and trading data for securities traded on the Asx New Trading Platform via Ip multicast.

### Overview

Ntp Itch is the Asx Market Data Protocol (Mdp) for the New Trading Platform, providing a high-speed binary market data service that distributes reference and trading data over Ip multicast. The protocol is built on Itch-style order-by-order events and delivers order add, modify, cancel, trade, and auction messages for all instruments traded on Asx Ntp.

The Mdp service consists of three complementary components. Multicast market data carries the real-time stream of reference and trading events. Blink is a Tcp recovery service that replays messages missed on the multicast feed. Glance is a Tcp snapshot service that provides on-demand full book snapshots so that subscribers can initialise state mid-day or after a gap.

### Transport

Udp multicast for real-time delivery of reference and trading data messages, carrying heartbeat-paced sequenced binary messages across the live market data feed. Tcp to the Blink recovery service for replay of missed multicast messages and to the Glance snapshot service for on-demand full book snapshots.

### Key Characteristics

- **Order-by-order** - Full depth of book reconstruction from individual order events
- **Multicast delivery** - Real-time Ip multicast distribution of the market data stream
- **Blink recovery** - Tcp replay service for gap recovery of missed multicast messages
- **Glance snapshot** - Tcp snapshot service for on-demand full book initialisation
- **Reference data** - Security definition and trading status messages integrated with the feed
- **Auction messages** - Equilibrium price update messages for auction events
- **Heartbeat paced** - Periodic heartbeat messages on the multicast feed
- **Binary encoded** - Compact fixed-width messages for low latency processing

