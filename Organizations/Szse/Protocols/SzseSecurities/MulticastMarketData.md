## SzseSecurities Multicast Market Data: Szse Multicast Market Data

Real time market data of the Shenzhen Stock Exchange fifth generation trading system, delivered by multicast from the Market Data Gateway. The feed publishes periodic snapshots of the order book for cash auction equities, funds and bonds, bond pledged repo, bond distribution, spot bond trading, after-hour-trading and after-hour-trading block trade, eligible Hong Kong stocks, indices, statistic indicators and the real time reference net value of funds, together with order and transaction tick data, the real time status of the market and of each security, channel statistics and announcements. Market data is divided into categories by business and each category is spread across as many numbered channels as its volume requires.

### Overview

Market data is addressed by channel rather than by specification. One multicast feed carries every product, and a subscriber selects what it receives by configuring its gateway for particular channels. The channel code ranges are fixed by business: 1 for real time market status, 2 for announcements, 10 to 12 for indices, statistics and fund net values, 101x to 107x for snapshot data by instrument class, 201x to 207x for auction tick data, 300x and 301x for after-hour-trading, 400x and 401x for comprehensive financial services and bond quotation, and 5001 for eligible Hong Kong stocks.

Snapshot messages and tick messages are a single message each whose body ends in extended fields selected by the message type, so the message type identifies both what the message is and which instrument class it describes. The market data category, carried in every message as MDStreamID, narrows it further; several categories map onto the same message type.

Two senders run as backups for each other on the same multicast address and port, distinguished by the Sender Id in the packet header. A receiver detects a data source restart either from a change of Sender Id or from a sequence number that has fallen back further than the configured out of order threshold, and resets its next expected sequence number from the latest packet.

Snapshot data is published on a cycle rather than on change. A changed snapshot is republished every 3 seconds and a full snapshot every 30 seconds whether or not anything has changed, so a subscriber that joins mid session recovers the whole book within one full cycle without a retransmission request.

### Transport

Multicast through the Market Data Distribution Protocol, which packs several complete application messages into one packet behind a table of their lengths and checks the whole packet with Adler32. A multicast flow is identified by address, port and sender, and a data flow by the flow and channel. Snapshot data cannot be re-transmitted; tick data is recovered through a Market Data Gateway session.

### Key Characteristics

- **Channel addressed** - Every product shares one feed, separated by numbered channel and market data category
- **Packed packets** - Several complete application messages per packet behind an optional table of their lengths
- **Adler32 checked** - One packet level checksum replaces the per message checksum of the session encoding
- **Cyclic snapshots** - Changed snapshots every 3 seconds and full snapshots every 30 seconds, so the book self heals
- **Order by order ticks** - Order and transaction tick data share one consecutive sequence per channel
- **Nested book disclosure** - Market data entries carry price levels, and each level the individual order quantities behind it
- **Redundant senders** - Two senders back each other on one address and port, distinguished by Sender Id
- **Optional compression** - A packet body may be zlib compressed, flagged in the packet header

