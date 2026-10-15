## CfeFutures Oof Multicast Depth Of Book: Cboe Futures Options On Futures Depth Of Book Data

Full depth of book Pitch feed publishing order add, modify, cancel, and execute events for options on futures (OOF) traded on Cboe Futures Exchange (CFE).

### Overview

OOF Depth Of Book is the full depth of book market data feed for options on futures traded on Cboe Futures Exchange (CFE). The specification describes it as essentially the CFE Multicast PITCH protocol with the addition of CFE options specific messages: OOF Symbol Mapping (0xF9) maps each option feed symbol to its strike, put/call, expiration and underlying future, and Complex Instrument Definition Expanded (0x9A) defines multi-leg option strategies.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Options on futures** - Option symbol mapping and complex instrument definitions
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy

