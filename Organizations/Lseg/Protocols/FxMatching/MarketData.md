## FxMatching Market Data: Market Data

Unscreened conflated level 2 market data for LSEG FX Matching spot instruments in Simple Binary Encoding, carried on separate snapshot, incremental, trades, security definition and statistics channels.

### Overview

Each market data group is a set of five feeds for one venue: snapshot full refresh at a per instrument interval, incremental refresh of the aggregated by price book at a per instrument conflation interval, the last trade of each trades conflation interval, security definitions, and trade derived statistics such as Vwap and the session high and low.

The incremental and trades feeds close every conflation interval with an End Marker, and a feed with no activity sends Heartbeats; packets carrying only a heartbeat repeat the sequence number of the next business packet.

### Transport

Udp multicast, each feed duplicated as an A and a B channel; every packet opens with a twenty byte binary packet header followed by one or more Sbe messages.

### Key Characteristics

- **Conflated level 2** - Aggregated by price book changes published per conflation interval
- **Unscreened prices** - Prices are not checked for bilateral credit
- **Machine-readable schema** - The wire layout is published as an Sbe message schema

