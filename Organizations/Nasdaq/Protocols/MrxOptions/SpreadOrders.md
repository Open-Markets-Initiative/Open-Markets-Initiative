## MrxOptions Spread Orders: Nasdaq Phlx Options Complex Order Component

Order Component of the Nasdaq Phlx Options Spread Feed: announcements of new complex resting orders and complex strategy auctions.

### Overview

Spread Orders is the Order Component of the Nasdaq Phlx Options Spread Feed. It advises participants that a new complex order is resting on the book and announces new complex auction orders (including exposure, price improvement, facilitation, solicitation, and flex auctions). Order updates are not provided and cannot be used to build the spread order book.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of complex order add and complex strategy auction messages. Tcp via SoupBinTcp for replay of missed multicast messages, terminated by an End of Replay Sequence message.

### Key Characteristics

- **Complex order announcements** - Complex Add Order messages for new resting complex orders
- **Complex strategy auctions** - Strategy Auction messages covering start, update, and end of complex auctions
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **SoupBinTcp replay** - SoupBinTcp recovery channel
- **Phlx Options** - Coverage of Nasdaq Phlx Options listed instruments

