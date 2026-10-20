## CfeFutures Oof Multicast Top: Cboe Futures Options On Futures Top Data

Multicast top of book feed publishing best bid and offer quotations and trades for options on futures (OOF) traded on Cboe Futures Exchange (CFE).

### Overview

OOF Top is the top of book market data feed for options on futures traded on Cboe Futures Exchange (CFE). It carries the same OOF Symbol Mapping (0xF9) and Complex Instrument Definition Expanded (0x9A) messages as the OOF depth of book feed alongside single side and two side top of book updates.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Options on futures** - Option symbol mapping and complex instrument definitions
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy

