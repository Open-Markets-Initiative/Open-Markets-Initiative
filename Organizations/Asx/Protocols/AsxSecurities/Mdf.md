## AsxSecurities Mdf: Asx Trade Price Level And Reference Market Data

Itch-like binary market data feed from the Asx Trade platform carrying price level depth, trade statistics, reference prices, indices, trade ticker and market announcements not found on the Itch feed.

### Overview

MDF complements Asx Trade Itch: it consolidates the order book to price levels and adds reference and market data Itch does not carry, including fixed income directory extensions, corporate action entries, instrument status, trade statistics, reference and index prices, open interest, a trade ticker, price limits and market announcements.

Messages use an Itch-like binary format with eight byte signed prices of four decimals, a Seconds message carrying Unix time and a nanosecond offset in every other message, and are distributed over MoldUdp64 with SoupBinTcp for Glimpse snapshots and recovery.

### Transport

Udp multicast via MoldUdp64, with a MoldUdp64 rewind gateway resending missed packets as unicast. Tcp via SoupBinTcp for the same feed and for the Glimpse snapshot and recovery services.

### Key Characteristics

- **Market by price** - Incremental price level depth
- **Reference data** - Order book, exchange, market, tick size, leg and corporate action directories
- **Trade ticker** - Every trade with deal source, participants and trade condition
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing

