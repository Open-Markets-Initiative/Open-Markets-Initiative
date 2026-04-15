## Binary Umdf: B3 Sbe Multicast Market Data

Sbe-encoded multicast market data protocol publishing order book, trade, and reference data for equities and derivatives traded on B3.

### Overview

Binary Umdf is the B3 Unified Market Data Feed delivered as a binary Sbe-encoded multicast stream. It publishes the full range of B3 market data including incremental order book updates in Mbo form, security definitions, trading status, settlement prices, open interest, and reference data for every instrument on the B3 equities and derivatives markets.

The wire format is based on Fix Simple Binary Encoding version 1.0, which targets high performance trading systems by keeping encoding and decoding optimized for low latency while constraining each message to fit within a single 1400 byte network packet. The encoding is complementary to Fix semantics for application-level message content while avoiding the chunking and bandwidth overhead of Fix/Fast.

### Transport

Udp multicast for real-time delivery of sequenced Sbe messages fitting within a 1400 byte packet, carrying incremental refresh, security definition, settlement price, and open interest messages.

### Key Characteristics

- **Sbe encoded** - Fix Simple Binary Encoding version 1.0 for fixed-width low-latency parsing
- **Multicast delivery** - Real-time Udp multicast distribution with sequence numbers
- **Order book Mbo** - Incremental depth of book refresh messages in market-by-order form
- **Settlement price** - Dedicated settlement price messages per instrument
- **Open interest** - Dedicated open interest messages for derivatives
- **Security reference** - Security definition messages integrated with the feed
- **Packet bounded** - Messages sized to fit within a 1400 byte network packet
- **Equities and derivatives** - Unified feed across B3 asset classes

