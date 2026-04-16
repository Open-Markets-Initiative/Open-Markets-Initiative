## Amd: Aquis Exchange Market Data

Binary market data protocol distributing real-time order, trade, and auction feeds for securities traded on Aquis Exchange via Ip multicast.

### Overview

Amd is the Aquis market data protocol, distributing real-time order and trade data for securities traded on Aquis Exchange over Ip multicast. The continuous feed publishes order add, cancel, modify, trade, and trade bust events, along with security definition and security status messages throughout the trading day.

Separate feeds carry Auction On Demand and Market at Close messages, and a snapshot feed publishes book state on a regular cadence for subscribers coming in after the start of the day. A Tcp replay service provides login-authenticated gap recovery for messages missed on the multicast feed, covering the full reliability path.

### Transport

Udp multicast for the continuous, auction, market at close, and snapshot feeds, carrying heartbeat-paced binary messages with per-packet sequence numbers for gap detection. Tcp to the replay service for login-authenticated gap recovery of missed messages from the multicast feed.

### Key Characteristics

- **Multicast distribution** - Ip multicast delivery of continuous, auction, and snapshot feeds
- **Order-level events** - Add, cancel, modify, trade, and trade bust messages for each order
- **Auction On Demand** - Dedicated feed for intra-day auction events
- **Market at Close** - Dedicated feed for closing auction events
- **Snapshot feed** - Periodic book state publication for late joiners
- **Replay service** - Tcp-based gap recovery with login authentication
- **Heartbeat paced** - Regular heartbeat messages on all multicast feeds
- **Security reference data** - Security definition and security status message types

