## Ntp Itch: Asx Securities Market Data

Ntp Itch market data feed for Asx securities on the National Trading Platform.

### Overview

Ntp Itch is the binary market data protocol for the Asx National Trading Platform, disseminating real-time order book and trade data for equities, warrants, and related securities. The feed delivers order-by-order messages enabling subscribers to reconstruct the full depth of book.

The protocol carries order add, modify, and delete events along with trade reports, instrument reference data, and trading status updates. Subscribers process the sequential message stream to maintain an accurate view of the Ntp order book throughout the trading session.

### Transport

Udp multicast with sequence numbers for gap detection and snapshot feeds for recovery.

### Key Characteristics

- **Order-by-order** - Individual order events for complete book reconstruction
- **Full depth of book** - Every order visible at every price level
- **Trade reporting** - Last sale data with trade condition indicators
- **Binary encoded** - Compact fixed-length messages for efficient processing
