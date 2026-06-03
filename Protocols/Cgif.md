## Cgif: Cboe Global Indices Feed

Cboe Global Indices Feed (CGIF) — a Cboe-published binary market data protocol carrying calculated index values, deployed under the Cboe Titanium Consolidated infrastructure. Packet header announces version, length, sending time, message count, and first message sequence number; each message has a length + template id prefix dispatching to per-template payload types (Index Value, Heartbeat, Channel Reset, etc.).

### Overview

Cgif is the Cboe Global Indices Feed encoding, a streamlined binary market data protocol that disseminates real-time index values, descriptive metadata, and channel mapping information for indices computed and published by Cboe Global Markets. The feed covers a wide range of equity, volatility, options-based, and proprietary Cboe indices.

The wire format uses fixed-width binary headers followed by repeating MDEntry groups whose count is determined by a NoMDEntries field. Symbol, description, and channel fields are variable length and preceded by length bytes for efficient on-the-wire packing. The protocol uses little-endian byte ordering consistent with other Cboe Titanium market data feeds.

Cgif is delivered alongside other Cboe market data products under the Titanium infrastructure, sharing the standard sequenced-packet recovery semantics with the Pitch family. Subscribers receive both incremental index updates and snapshot messages, with the snapshot stream available for mid-day initialisation and recovery.

### Transport

Cgif is delivered via UDP multicast. Each packet carries the standard Cgif packet header followed by a count of length-prefixed messages.

### Key Characteristics

- **Index data dissemination** - Real-time index value updates for Cboe Global Markets indices
- **Streamlined binary encoding** - Little-endian fixed-width binary headers with variable-length descriptor fields
- **Repeating MDEntry groups** - One or more MDEntry records per packet controlled by a NoMDEntries count
- **Variable-length descriptors** - Symbol, Description, and Channel fields sized by preceding length bytes
- **Udp multicast delivery** - A and B feed redundancy under the Cboe Titanium multicast infrastructure
- **Sequenced recovery** - Per-packet sequence numbers compatible with Cboe gap detection

