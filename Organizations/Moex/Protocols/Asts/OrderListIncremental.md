## Asts Order List Incremental: SIMBA ASTS Order List Refresh

Incremental updates to the list of active orders of the Moex equities and currency markets: new best prices, empty books, order additions, changes and deletions, executions and trades. Each packet carries a market data packet header, an incremental packet header stating the transaction time and trading session, and one or more Sbe messages. New best prices are published in a packet of their own ahead of the order updates of the transaction that changed them.

### Overview

Incremental packet sequence numbers are reset to one when the gateway starts or restarts. A transaction too large for one packet is split across packets, every packet but the last marked Last Fragment 0 in the packet header.

New best prices are published only when a transaction changes at least one best price; a volume change at the same price is not published, and a side left empty is sent as a null price.

### Transport

Udp multicast, every message sent as identical copies to Incremental Feeds A and B on separate groups, with a heartbeat each second the channel has nothing else to send.

### Key Characteristics

- **Order list** - Order by order additions, changes, deletions and executions
- **Best prices first** - New best prices are sent ahead of the order updates that caused them
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Paired multicast streams** - Every message is sent on Feeds A and B for arbitration

