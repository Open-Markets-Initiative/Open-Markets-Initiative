## BruceEquities Depth Of Book: Bruce Ats Depth Of Book Data

Order-by-order depth of book feed publishing add, modify, and execute events for securities traded on The Bruce Ats equities platform.

### Overview

Bruce Depth Of Book is a direct market data feed delivering the complete order book for securities traded on The Bruce Ats. The feed publishes order add, modify, execute, and cancel events that allow subscribers to reconstruct the full depth of book for every listed instrument during the trading session.

The protocol is made up of a series of sequenced messages with each message variable in length based on message type, delivered over MoldUdp64 which provides packet-level sequencing and gap detection. Instruments are identified by a stock locate code assigned dynamically each day via the Stock Directory message, and the feed also carries system events, trading actions, and Reg SHO short sale price test restricted indicators.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style depth of book messages, with packet-level sequencing for gap detection.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, and execute events
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Itch encoded** - Variable length Itch-style binary messages
- **Stock locate codes** - Dynamic integer identifiers assigned each day via Stock Directory
- **Order lifecycle** - Add, modify, execute, and cancel events
- **Trading actions** - Per-instrument trading status notifications
- **Reg SHO** - Short sale price test restricted indicator updates

