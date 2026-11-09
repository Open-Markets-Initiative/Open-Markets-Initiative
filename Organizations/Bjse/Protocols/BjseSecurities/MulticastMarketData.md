## BjseSecurities Multicast Market Data: Bjse Multicast Market Data

Real time market data of the Beijing Stock Exchange, delivered by multicast from the market quotation gateway (BJQG) shared with the National Equities Exchange and Quotations. The feed publishes snapshots, order ticks and trade ticks of spot bond trading, the real time status of each security, channel statistics and announcements; snapshots of centralized auction trading and indices, and ticks of the trading support platform, are documented but not yet enabled.

### Overview

Market data is addressed by channel rather than by specification. A subscriber selects what it receives by configuring its gateway for particular channels: 1 for real time security status, 2 for announcements, 3 for index snapshots, 101x for spot bond trading snapshots, 102x for centralized auction snapshots, 201x for spot bond trading ticks, and 204x to 207x for the trading support platform ticks.

Snapshot messages and tick messages share a common body that most message types follow with extension fields of their own, so the message type identifies both what the message is and which business it describes. The market data category, carried in every message as MDStreamID, matches it.

Two senders run as backups for each other on the same multicast address and port, distinguished by the Sender Id in the packet header. A receiver detects a data source restart either from a change of Sender Id or from a sequence number that has fallen back further than a configured out of order threshold, and resets its next expected sequence number from the latest packet.

Snapshot data is published periodically, each category at its own frequency, and cannot be retransmitted; tick data is published in real time and is recovered through a market quotation gateway session.

### Transport

Multicast through the Market Data Distribution Protocol, which packs several complete application messages into one packet, optionally behind a table of their lengths, and checks the whole packet with Adler32. A multicast flow is identified by address, port and sender, and a data flow by the flow and channel.

### Key Characteristics

- **Channel addressed** - Every business shares one feed, separated by numbered channel and market data category
- **Packed packets** - Several complete application messages per packet behind an optional table of their lengths
- **Adler32 checked** - One packet level checksum replaces the per message checksum of the session encoding
- **Order by order ticks** - Order and trade tick data share one consecutive sequence per channel
- **Redundant senders** - Two senders back each other on one address and port, distinguished by Sender Id
- **Optional compression** - A packet body may be zlib compressed, flagged in the packet header

