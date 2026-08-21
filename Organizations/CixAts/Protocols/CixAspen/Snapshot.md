## CixAspen Snapshot: CIX Tcp Snapshot Recovery

Login authenticated Tcp snapshot service that rebuilds current book state for the CIX Market Data Feed, replaying market, symbol and resting order messages inside the TcpOut encapsulation layer and closing with an End of Snapshot marker.

### Overview

Snapshot is the fast catch-up recovery path for the CIX Market Data Feed, letting a recipient rebuild current book state intra-day rather than replaying every missed message. Clients log in with a username and password over Tcp and must request sequence 1; the server answers with a Successful Login carrying the Market Day Identifier, Feed Identifier and the sequence number of the next Binary Data message, or a Login Reject naming the reason.

The snapshot delivers all Market Event, Symbol Information and Symbol State messages. For order specific messages only orders currently on the books are sent, so New Order Add, Order Partial Cancel, Order Cancel All and Order Executed appear while Trade, Trade Cancel and Trade Correct do not. An End of Snapshot message closes the snapshot and names the multicast sequence number where it ends.

Because the feed keeps moving while the snapshot is being delivered, recipients are expected to subscribe to CIX multicast before or during the snapshot and hand off at the End of Snapshot sequence, using the Udp rerequest path for anything still missing after switchover. CIX runs a Primary and a Secondary snapshot server per feed, with only one typically active; clients should try Primary first and fall back to Secondary.

### Transport

Tcp session over the TcpOut encapsulation layer, opened with a username and password Login and paced by heartbeats in both directions, carrying the snapshot as a sequence of Binary Data messages.

### Key Characteristics

- **Book state recovery** - Rebuilds current book state rather than replaying every missed message
- **Authenticated session** - Username and password Login with an explicit accept or reject response
- **Resting orders only** - Order messages are limited to orders currently on the books
- **End of Snapshot marker** - Names the multicast sequence number where the snapshot ends, for handoff
- **Bidirectional heartbeats** - Client heartbeats at least once per second, server heartbeats when otherwise idle
- **Primary and Secondary** - Paired snapshot servers per feed with client side failover

