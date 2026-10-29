## Emdi: Enhanced Market Data Interface

Bse's un-netted price level market data feed, disseminating every order book change up to the configured depth and every on-exchange trade without netting. Its incremental feed carries the order book updates, product and instrument state changes, instrument updates, quote and cross requests and index changes, encoded as Fix 5.0 Sp2 messages in Fast 1.2 on Ip multicast.

### Overview

Bse Emdi is a licensed deployment of the T7 Enhanced Market Data Interface. Every Udp datagram is self contained: it opens with a Fast encoded packet header, then a Fast reset message that clears every dictionary, then one or more Fast encoded messages, so a datagram decodes without the ones before it. All operators share one global dictionary regardless of template and application type.

Each message is a presence map, a template id and a data part. Bse publishes the templates as Xml in two forms, one for Fast 1.2 decoders, which uses the 1.2 enumeration and set definitions, and one compatible with Fast 1.1, which leaves the codes undefined; both encode the same messages.

The incremental feed is the one to stay subscribed to throughout the day. A recipient that has lost data or joins late rebuilds the book from the separate Emdi snapshot feed, whose snapshots carry the last incremental sequence number they include.

### Transport

Ip multicast incremental channels, partitioned so that each carries a group of similar products, with the snapshots delivered out of band on channels of their own.

### Key Characteristics

- **Un-netted** - Every order book change up to the configured depth and every on-exchange trade
- **Price level book** - Aggregated price levels rather than individual orders
- **Self contained datagrams** - A packet header and a dictionary reset open every datagram
- **Out of band snapshots** - Snapshots are delivered on channels separate from the incremental feed
- **Fast 1.2** - Fix 5.0 Sp2 messages Fast encoded, with Fast 1.1 compatible templates also published

