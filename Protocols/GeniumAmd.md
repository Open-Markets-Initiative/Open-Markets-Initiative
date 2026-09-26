## GeniumAmd: Nasdaq Genium INET AMD

Binary market data protocol of the Nasdaq Genium INET trading platform, which the document calls an ITCH-like direct data feed product, carrying reference data, reported trades, quote requests and aggregated depth for the derivatives and commodities markets the platform runs. Named AMD by Nasdaq, and unrelated to the Aquis Market Data protocol that shares the abbreviation.

### Overview

Genium INET is the Nasdaq trading platform licensed to exchanges and clearing houses worldwide, and AMD is its aggregated market data feed. Where the Itch feeds of the Nasdaq equity markets publish every order, AMD publishes the state of the book by price level together with the reference data, trades and quote requests a participant needs to follow the market.

The protocol declares five data types and no more: a Numeric of one, two, four or eight bytes read as an unsigned big endian integer, an Alpha of any width left justified and padded with spaces, a signed Price, a four byte Date read as YYYYMMDD and an eight byte Datetime read as YYYYMMDDHHmmSSsss. A price carries no scale of its own - the Order book Directory states how many decimals the order book uses - so the number on the wire is an integer until a reader places the point.

Timestamps are split in two for bandwidth: a Seconds message carries Unix time once for every second in which anything happens, and each message after it carries only the nanoseconds since that Seconds message. A reader adds the two to recover when the trading system generated the message.

### Transport

AMD is disseminated over MoldUDP64, which frames a sequenced stream of messages into datagrams and lets a receiver detect and recover a gap by sequence number. The message bodies are big endian, which the document states once for the whole protocol by way of the transport. The same messages are served over SoupBinTcp for recovery and for a session that wants a reliable ordered stream rather than multicast.

### Key Characteristics

- **Aggregated depth** - Publishes the book by price level rather than order by order
- **Big endian** - Stated once for the protocol, by way of the transport it runs on
- **Split timestamps** - A Seconds message carries the second, each message the nanoseconds within it
- **Runtime price scale** - The Order book Directory states the decimals, so a price is an integer on the wire
- **Genium INET native** - The feed of the platform Nasdaq licenses for derivatives and commodities markets

