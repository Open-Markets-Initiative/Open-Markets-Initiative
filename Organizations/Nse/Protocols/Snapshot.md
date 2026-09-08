## Snapshot: Mtbt Order Book Snapshot Recovery

Nse's Tcp order book snapshot service for the tick by tick market data feed. The Order Book Snapshot Recovery Server holds a picture of the book built from the Mtbt feed and refreshed every thirty seconds, and serves it as a single buffer of outstanding orders so that a client joining late, or one that has lost a large number of ticks, can rebuild its book without replaying them.

### Overview

The snapshot buffer does not use the stream header of the multicast feed. It opens with its own sixteen byte snapshot header carrying a transcode of 10501, the total size of the buffer, the number of order records that follow, the last multicast sequence number the snapshot includes, and the stream identifier.

Only outstanding orders appear in a snapshot, so every record is a new normal order or a new spread order. The record layout is the same as the corresponding message on the multicast feed.

The last sequence number in the header is what joins a snapshot to the live feed: a client applies the snapshot, then resumes from the following sequence number on multicast or through the recovery service.

### Transport

Snapshot session carrying a request, a status response, and one buffer holding every outstanding order for the stream.

### Key Characteristics

- **Point in time** - The book image is refreshed every thirty seconds and served as it stood at the last refresh
- **Self framing** - A sixteen byte snapshot header replaces the multicast stream header and counts the records that follow
- **Outstanding orders only** - Records are limited to new normal and new spread orders still resting in the book

