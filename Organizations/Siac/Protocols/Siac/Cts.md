## Cts: Siac Consolidated Tape Last Sale Feed

Consolidated last sale feed for listed equities published by Siac on behalf of the Consolidated Tape Association delivering trade reports from Tape A and Tape B participants.

### Overview

The Consolidated Tape System (Cts) is the last sale reporting feed for Nyse-listed and Nyse Amex-listed securities (Tape A and Tape B). It is published by the Securities Industry Automation Corporation (Siac) on behalf of the Consolidated Tape Association and delivers trade messages from all reporting participants as a single consolidated last sale stream.

Messages are distributed over Ip multicast using the Cta output line format, with sequenced trade messages, trade cancellations, trade corrections, and administrative events. A companion Tcp re-request service provides gap recovery for subscribers that miss messages on the multicast feed, giving the full reliability path expected of a regulated consolidated tape.

### Transport

Udp multicast for real-time delivery of consolidated tape trade messages over sequenced Cta-format datagrams with per-packet sequence numbers for gap detection. Tcp for the Consolidated Tape re-request and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Consolidated last sale** - Tape A and Tape B trade messages in one stream
- **Cta format** - Industry-standard Consolidated Tape Association output line format
- **Multi-participant** - Aggregates trade reports from all reporting exchanges
- **Multicast delivery** - Real-time Udp multicast distribution with sequence numbers
- **Trade lifecycle** - Trade report, cancel, and correction messages
- **Re-request service** - Tcp recovery service for missed multicast messages
- **Regulated tape** - Operated by Siac on behalf of the Consolidated Tape Association

