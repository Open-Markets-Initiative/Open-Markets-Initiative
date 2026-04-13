## Pts Bonds Itch: Jnx Market Data

Pts Itch market data feed for bonds traded on the Japannext proprietary trading system.

### Overview

Pts Bonds Itch is the market data protocol used by Japannext to distribute real-time order-by-order data for bonds on the Jnx Pts venue. The feed delivers individual order add, modify, delete, and execution messages, enabling subscribers to reconstruct the complete limit order book for all listed bond instruments.

The protocol carries reference data, trading status, order book events, and trade messages for the bond market throughout the trading session. Subscribers process the sequential message stream to build and maintain an accurate representation of the bond order book.

### Transport

Tcp with MoldUdp64-style session layer providing sequencing and session management.

### Key Characteristics

- **Order-by-order** - Individual order add, modify, delete, and execution messages
- **Full book depth** - Complete order book reconstruction from order-level events
- **Bonds focused** - Covers all bond instruments on the Jnx Pts
- **Sequential stream** - Ordered message stream with sequence numbers
