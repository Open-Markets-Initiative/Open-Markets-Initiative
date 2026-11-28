## Asts Instrument Status: SIMBA ASTS Instrument Status

Incremental changes to the trading modes of Moex equities and currency market securities and to the trading session status. Published incrementally, but each packet in the snapshot packet format: a market data packet header and a single Sbe message.

### Transport

Udp multicast, every message sent as identical copies to Incremental Feeds A and B on separate groups.

### Key Characteristics

- **Status changes** - Security and trading session status updates
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Paired multicast streams** - Every message is sent on Feeds A and B for arbitration

