## Pts SecurityToken Itch: Odx Market Data

Pts Itch market data feed for security tokens traded on the Osaka Digital Exchange START platform.

### Overview

Pts SecurityToken Itch is the market data protocol used by Odx to distribute real-time order-by-order data for security tokens on the Odx START venue. The feed delivers individual order add, modify, delete, and execution messages, enabling subscribers to reconstruct the complete limit order book for all listed security token instruments.

The protocol carries reference data, trading status, order book events, and trade messages for the security token market throughout the trading session. Subscribers process the sequential message stream to build and maintain an accurate representation of the security token order book.

### Transport

Tcp with MoldUdp64-style session layer providing sequencing and session management.

### Key Characteristics

- **Order-by-order** - Individual order add, modify, delete, and execution messages
- **Full book depth** - Complete order book reconstruction from order-level events
- **Security tokens focused** - Covers all security token instruments on the Odx START platform
- **Sequential stream** - Ordered message stream with sequence numbers
