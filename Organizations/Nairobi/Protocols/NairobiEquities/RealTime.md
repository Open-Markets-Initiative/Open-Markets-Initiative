## NairobiEquities Real Time: Nairobi Equities Real Time

Real time market data of the Nairobi Securities Exchange equity trading system: the instruments of each market data group, their trading status, order book updates, auction information, trades, statistics, indices and announcements, delivered by multicast.

### Overview

Every application message is sequenced within its market data group, the sequence resetting to 1 each day. A unit header carries the sequence number of its first message and each following message is one greater, so a gap is detected from the sequence number and message count.

Timestamps are nanosecond offsets from the most recent Time message, which carries the seconds since midnight in the server's local time and is sent for every second in which an application message is generated.

A recipient may arbitrate between Feed A and Feed B to minimise data loss, recovering a small loss on the Replay channel and a large one, or a late join, on the Snapshot channel.

### Transport

Multicast per market data group, from a main site (Feed A) and a backup site (Feed B) carrying identically sequenced streams. Each unit header carries the sequence number of its first message; a unit header with no messages is the heartbeat, sent at an interval of inactivity the document leaves as a placeholder (<2> seconds).

### Key Characteristics

- **Dual feeds** - Identically sequenced Feed A and Feed B from the main and backup sites
- **Sequenced units** - A unit header carries the first sequence number and a message count
- **Relative timestamps** - Nanosecond offsets from the most recent Time message
- **Heartbeat units** - An empty unit header during inactivity carries the next sequence number

