## TitaniumConsolidated Indices: Global Indices Feed

Cboe Global Indices Feed — consolidated real-time index value, descriptor, and channel mapping feed for indices computed and published by Cboe Global Markets, delivered under the Cboe Titanium infrastructure.

### Overview

Indices is the Cboe Global Indices Feed, a consolidated real-time market data product disseminating index values for the broad range of equity, volatility, options-based, and proprietary indices computed and published by Cboe Global Markets. Subscribers receive periodic index value updates plus descriptor and channel-mapping messages that identify each published index.

The feed is delivered over Udp multicast with A and B feed redundancy and per-packet sequence numbers, sharing the standard Cboe Titanium recovery semantics. Each packet carries one or more MDEntry records using the streamlined Cgif binary encoding with variable-length Symbol, Description, and Channel descriptors.

### Transport

Udp multicast via the Cgif framing for real-time delivery of sequenced index value updates with per-packet sequence numbers and A and B feed redundancy.

### Key Characteristics

- **Index dissemination** - Real-time updates for Cboe Global Markets indices across asset classes
- **Cboe Cgif binary** - Streamlined little-endian binary format with variable-length descriptors
- **Udp multicast** - A and B feed redundancy under the Cboe Titanium multicast infrastructure
- **Sequenced recovery** - Per-packet sequence numbers compatible with Cboe gap detection
- **Symbol descriptors** - Channel mapping and description records identify each published index

