## Emdi Snapshot: Enhanced Market Data Interface Snapshot

The snapshot feed of Bse's Enhanced Market Data Interface, carrying time driven depth snapshots of the order book that a recipient uses to recover lost market data or to build up the current book before applying the Emdi incremental feed. Bse publishes its templates in a file of their own, EMDSFastTemplates, encoded as Fix 5.0 Sp2 messages in Fast 1.2 on Ip multicast.

### Overview

Emdi delivers its snapshots out of band. Each depth snapshot carries the last message sequence number processed on the incremental feed, which is the link a recipient uses to discard the buffered incremental messages the snapshot already includes and apply the rest. Recipients are not expected to stay subscribed to the snapshot feed.

The datagram framing is the Emdi framing: a Fast encoded packet header, a Fast reset message that clears the global dictionary, then the Fast encoded messages.

### Transport

Ip multicast snapshot channels, separate from the Emdi incremental channels, that a recipient joins only while recovering.

### Key Characteristics

- **Time driven** - Depth snapshots are sent cyclically rather than on order book events
- **Recovery link** - Each snapshot states the last incremental sequence number it includes
- **Self contained datagrams** - A packet header and a dictionary reset open every datagram
- **Fast 1.2** - Fix 5.0 Sp2 messages Fast encoded, with Fast 1.1 compatible templates also published

