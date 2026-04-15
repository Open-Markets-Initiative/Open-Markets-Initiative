## Cqs: Siac Consolidated Quote Feed

Consolidated quotation feed for listed equities published by Siac on behalf of the Consolidated Tape Association delivering best bid and offer updates from Tape A and Tape B participants.

### Overview

The Consolidated Quotation System (Cqs) is the consolidated quotation feed for Nyse-listed and Nyse Amex-listed securities (Tape A and Tape B). It is published by the Securities Industry Automation Corporation (Siac) on behalf of the Consolidated Tape Association and delivers quote updates from all reporting exchanges as a single consolidated stream.

Messages are distributed over Ip multicast using the Cta output line format with sequenced quote updates, best bid and offer changes, limit up limit down events, administrative messages, and trading halts. A companion Tcp re-request service provides gap recovery for subscribers that miss messages on the multicast feed, giving the full reliability path expected of a regulated consolidated quote.

### Transport

Udp multicast for real-time delivery of consolidated quote messages over sequenced Cta-format datagrams with per-packet sequence numbers for gap detection. Tcp for the Consolidated Quotation re-request and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Consolidated quotes** - Tape A and Tape B quote updates in one stream
- **Cta format** - Industry-standard Consolidated Tape Association output line format
- **Multi-participant** - Aggregates quote updates from all reporting exchanges
- **Multicast delivery** - Real-time Udp multicast distribution with sequence numbers
- **Limit up limit down** - Luld band messages for price bands and trading pauses
- **Trading halts** - Administrative halt and resumption messages
- **Re-request service** - Tcp recovery service for missed multicast messages
- **Regulated feed** - Operated by Siac on behalf of the Consolidated Tape Association

