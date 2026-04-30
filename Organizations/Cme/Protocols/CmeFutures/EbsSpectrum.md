## CmeFutures Ebs Spectrum: Cme Ebs Spectrum Spot Foreign Exchange Market Data

Cme Ebs Spectrum market data feed distributing spot foreign exchange price discovery, depth of book, and trade summary messages for major, minor, and emerging market currency pairs traded on the Cme Ebs Spectrum platform. Delivered as conflated SBE messages over UDP multicast.

### Overview

Ebs Spectrum is Cme's spot foreign exchange trading platform, offering electronic trading of major, minor, and emerging market currency pairs. The Ebs Spectrum market data feed distributes price discovery, top-of-book, depth-of-book, and trade summary messages aggregated from the central limit order book and negotiated block trades on the venue. The data flow is independent of the Ebs Spectrum order entry protocol and is intended for subscribers who observe the market without posting orders.

Messages are encoded in Cme's Simple Binary Encoding (SBE), the same wire format used across the Market Data Platform 3.0 family, and carried over UDP multicast with a nominal conflation interval that aggregates events within a small time window to keep bandwidth bounded while preserving market state fidelity. Each packet begins with the Cme BinaryPacketHeader providing a 32-bit packet sequence number and 64-bit sending time so receivers can detect gaps, compute latency, and order events across channels.

Recovery follows the standard Cme market data pattern — subscribers request missed packets from the dedicated TCP replay service, refresh instrument state from the instrument definition channel, and join the market recovery snapshot multicast group to re-synchronise after a prolonged gap. Certification of consuming applications is performed via AutoCert+ using the Ebs Spectrum Market Data (Conflated UDP Ultra) test environment.

### Transport

Udp multicast for dual-feed A/B delivery of conflated SBE-encoded depth and trade summary messages. Cme's Market Data Platform wraps each datagram in the BinaryPacketHeader carrying packet sequence number and nanosecond sending time so subscribers can detect gaps and recover against the TCP replay service. Tcp for market data replay, market recovery snapshots, and instrument definition dissemination over the shared Cme Smart Stream / Market Data Platform services.

### Key Characteristics

- **Spot foreign exchange** - Major, minor, and emerging market currency pairs traded on Cme Ebs Spectrum
- **Depth of book** - Market by Price with configurable depth plus trade summary events
- **SBE over UDP multicast** - Simple Binary Encoding carried over dual-feed UDP multicast for efficient dissemination
- **Conflated** - Events aggregated within a short conflation window to bound bandwidth while preserving order-book state
- **Packet sequenced** - BinaryPacketHeader packet sequence number and sending-time timestamp for gap detection
- **Dual-feed** - Feed A and feed B multicast groups carry identical messages for arbitration on the receiver side
- **TCP replay recovery** - Missed packets recovered via the dedicated Cme TCP market data replay service
- **Instrument definition channel** - Separate multicast group delivers instrument reference data and trading status updates

