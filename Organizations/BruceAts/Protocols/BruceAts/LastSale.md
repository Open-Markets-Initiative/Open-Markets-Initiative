## Last Sale: Bruce Ats Last Sale Trade Data

Trade feed publishing executed trade reports and cancellations for securities traded on The Bruce Ats equities platform.

### Overview

Bruce Last Sale is a direct market data feed delivering executed trade activity for securities traded on The Bruce Ats. The feed publishes trade report and trade cancellation messages as executions occur, providing subscribers with a clean last-sale stream without the overhead of a full depth feed.

Messages are delivered over MoldUdp64 multicast which provides packet-level sequencing and gap detection. Instruments are identified by a stock locate code assigned dynamically each day via the Stock Directory message, and the feed also carries system events, trading actions, and Reg SHO short sale price test restricted indicators to give subscribers a self-contained view of the market state.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style trade messages, with packet-level sequencing for gap detection.

### Key Characteristics

- **Last sale** - Executed trade reports with price, size, and conditions
- **Trade cancellations** - Cancellation messages for previously reported trades
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Itch encoded** - Fixed-width Itch-style binary messages
- **Stock locate codes** - Dynamic integer identifiers assigned each day via Stock Directory
- **Trading actions** - Per-instrument trading status notifications
- **Reg SHO** - Short sale price test restricted indicator updates

