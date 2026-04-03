## EbsSpectrum: Cme Ebs Derived Market Data

Sbe-encoded derived market data feed for Ebs Fx spot and forward markets on the Cme Globex platform.

### Overview

The Cme Ebs Spectrum feed delivers derived and calculated market data for foreign exchange instruments traded on the Ebs platform, which Cme Group acquired from Nex Group in 2018. The feed provides Vwap (volume weighted average price), Twap (time weighted average price), touch high/low, market high/low, open/close best bid and offer, and ticker data across multiple market hours sessions.

Messages include MdIncrementalRefreshSpectrum for derived data and MdIncrementalRefreshTicker for real-time ticker updates. Market hours sessions cover Global, Sydney, Tokyo, Hong Kong/Singapore, London, and New York time zones. The protocol includes a previous day flag to distinguish current day entries from prior business day data.

### Transport

Udp multicast with Sbe-encoded messages. Same packet structure as Mdp 3.0 feeds. Messages carry an EventIndicator bitfield marking recovery messages and end-of-event boundaries.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields with little-endian byte ordering
- **Fx derived data** - Vwap, Twap, touch high/low, market high/low, and ticker data
- **Market hours sessions** - Global, Sydney, Tokyo, Hong Kong/Singapore, London, and New York
- **Previous day flag** - Distinguishes current day entries from prior business day data
- **Recovery indicator** - Bit flag marking messages sent during recovery that may be duplicates
- **Nanosecond timestamps** - Publication time in nanoseconds since Unix epoch
