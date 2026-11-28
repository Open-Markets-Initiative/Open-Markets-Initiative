## Asts Order List Snapshot: SIMBA ASTS Order List Snapshot

Periodic snapshots of the list of active orders of the Moex equities and currency markets, one order book snapshot per board and security, for late joiners and recovery against the order list refresh channel. Each packet carries a market data packet header and a single Sbe message.

### Overview

Snapshot packets are numbered from one at the start of each snapshot cycle. The first packet of a security's snapshot is flagged Start Of Snapshot and the last End Of Snapshot, both on a snapshot that fits one packet.

A recipient rebuilds a book by queuing the incremental channel, applying the snapshots, then applying the queued messages whose Msg Seq Num is above the snapshot's Last Msg Seq Num Processed, or whose Rpt Seq is above the snapshot's.

### Transport

Udp multicast, every message sent as identical copies to Snapshot Feeds A and B on separate groups, throttled by a traffic shaper.

### Key Characteristics

- **Snapshot cycle** - Sequence numbers restart at one with every cycle
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Paired multicast streams** - Every message is sent on Feeds A and B for arbitration
- **Rate limited** - Transmission is throttled by a traffic shaper

