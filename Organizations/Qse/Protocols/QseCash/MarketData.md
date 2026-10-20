## QseCash Market Data: Qse Cash Market Data

Real time market data of the Qatar Stock Exchange cash market over the NYSE Technologies Universal Trading Platform, delivered as fixed layout binary messages on multicast streams. One specification serves Euronext and Qatar Exchange together and separates them by service id, Qatar Exchange taking 201 to 209 and system ids 101 to 109; this spec carries the 24 messages the document's per feed message type lists name for Qatar Exchange, and omits the eleven it marks as not used for Qatar or not disseminated at all.

### Overview

Every packet opens with the same 16 byte header, so a client implements line level protocol processing once and then develops parsing algorithms only for its choice of message. The header gives the packet length, the packet type, a per stream packet sequence number used for gap detection, a send time, the service id, a delivery flag and the number of messages in the packet. Each message that follows carries its own two byte size and two byte type.

The packet type names the generic feed when a packet mixes message types and otherwise repeats the single message type it carries. The generic types are 994 Quotes, 995 Market Information, 996 Indices, 998 Trades and 230 Orderbook, and 999 marks a refresh packet combining several of them.

Prices carry no scale of their own. A price is an integer divided by ten to the power of a scale code that travels beside it in the same message, so a consumer must read the scale code before it can value the price.

Gaps are recovered two ways. A retransmission server replays a small range of missed packets over a Tcp session addressed by begin and end packet sequence number, and a refresh server publishes the current market state on separate compressed multicast streams bracketed by a Start Refresh and an End Refresh message. Both sessions are kept alive by heartbeats the client must answer.

The binary layout is big endian, which separates this protocol from the later Nyse Xdp feeds that share the Exchange Data Publisher name and read every integer little endian. The two therefore cannot share a loader.

### Transport

Multicast streams, one service id per data product, each published on a Line A and a Line B group from a primary and a secondary source so a client receives two redundant feeds. Real time streams are uncompressed and the companion refresh streams carry the same messages ZliB compressed.

### Key Characteristics

- **Big endian** - Binary data is in network byte order, unlike the later Nyse Xdp feeds
- **Common packet header** - A 16 byte header on every packet, counting the messages that follow it
- **Length prefixed messages** - Each message carries a two byte size excluding itself and a two byte type
- **Runtime scaled prices** - A price is an integer valued against a scale code carried beside it, not a fixed number of decimal places
- **Compressed refresh** - Refresh multicast streams are ZliB compressed and flagged by the delivery flag, real time streams are not
- **Redundant lines** - Every service is published on a Line A and a Line B group from a primary and a secondary source
- **Shared specification** - One document serves Euronext and Qatar Exchange, separated by service id and system id

