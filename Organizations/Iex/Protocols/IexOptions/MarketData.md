## IexOptions Market Data: Iex Options Sbe Multicast Market Data

Sbe-encoded multicast Udp market data for Iex Options publishing top of market quotes, depth of book order events, trades, trading status, auction events, and instrument reference data.

### Overview

The Iex Options market data feeds share one Sbe message schema covering the full market data surface: underlying and instrument reference data, symbol mappings, trading status, quote updates for the top of market (Tops) products, order-level add, modify, delete, and execution events for the depth of book (Deep) products, trades, trade corrections and breaks, auction summaries, and liquidity event notifications.

Packets are framed by a two-byte little-endian length followed by a standard Sbe message header. Transport-level heartbeats, sequenced packets, session shutdown, retransmission requests and responses, and snapshot messages are themselves Sbe messages in the same schema, so the entire feed is decodable from the schema alone. A/B feed pairs provide first-line packet loss defense with gap fill and snapshot services for recovery.

### Transport

Udp multicast over the Iex Options Market Data Transport Protocol — length-framed Sbe packets with per-channel sequence numbers and A/B feed redundancy.

### Key Characteristics

- **Options market data** - Quotes, orders, trades, and instrument events for Iex Options
- **Sbe encoded** - Simple Binary Encoding with a shared schema across feeds
- **Length-framed packets** - Two-byte length prefix then Sbe header on every packet
- **Transport in schema** - Heartbeat, sequenced packet, and retransmission messages are Sbe messages
- **Channel pairs** - A and B feed redundancy with per-channel sequence numbers
- **Snapshot recovery** - Gap fill and snapshot services for out-of-band recovery

