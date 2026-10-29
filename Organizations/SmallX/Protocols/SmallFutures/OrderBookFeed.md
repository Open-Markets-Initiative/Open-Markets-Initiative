## SmallFutures Order Book Feed: Small Exchange Order Book Feed

Simple Binary Encoding market data feed of orders, trades, market state changes and instrument definitions for the Small Exchange market.

### Overview

The Small Exchange Order Book Feed allows market participants to receive market information such as updated orders, trades, market state changes and instrument definitions for the Exchange market. The feed consists of Market Data Channels, each distributing market data for a group of instruments.

Each channel has Incremental Lines, Udp multicast groups with sequenced real-time updates, and Snapshot Lines, which replay market data snapshots in cycles to give the initial market state when a session is established or re-established. A Retransmission Service resends messages lost on an Incremental Line. Messages are encoded with Simple Binary Encoding v1.0, little-endian.

### Transport

Udp multicast Incremental and Snapshot Lines, each with a sequence incrementing with each message sent, in packets of up to 1300 bytes.

### Key Characteristics

- **Order book feed** - Orders, trades, market state changes and instrument definitions
- **Incremental and snapshot lines** - Real-time sequenced updates, with snapshot cycles for the initial market state
- **Retransmission service** - Requests retransmission of messages lost on an Incremental Line
- **Simple Binary Encoding** - SBE v1.0, little-endian messages, headers and packet framing
- **Sequence numbered** - Each line has a sequence incrementing with each message sent

