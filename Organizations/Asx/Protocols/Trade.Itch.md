## Trade Itch: Asx Securities Market Data

Trade Itch market data feed for Asx exchange-traded options and futures on the Trade platform.

### Overview

Trade Itch is the binary market data protocol for the Asx Trade platform, disseminating real-time order book and trade data for exchange-traded options and futures. The feed provides order-by-order messages enabling subscribers to reconstruct the full depth of book for all derivatives listed on the Trade platform.

The protocol delivers order add, modify, and delete events, trade execution messages, instrument reference data, and trading status notifications. Subscribers process the sequential message stream to maintain an accurate representation of the Trade order book throughout the session.

### Transport

Udp multicast with sequence numbers for gap detection and snapshot feeds for recovery.

### Key Characteristics

- **Options and futures** - Exchange-traded derivatives on the Asx Trade platform
- **Order-by-order** - Individual order events for complete book reconstruction
- **Full depth of book** - Every order visible at every price level
- **Binary encoded** - Compact fixed-length messages for efficient processing
