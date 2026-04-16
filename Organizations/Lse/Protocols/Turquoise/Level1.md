## Turquoise Level1: Lse Turquoise Top Of Book Data

Level 1 top of book feed publishing best bid and offer quotations for securities traded on the Lse Turquoise Mtf.

### Overview

Turquoise Level 1 is a market data feed for the London Stock Exchange Turquoise Multilateral Trading Facility (Mtf), delivered via the Lseg Group Ticker Plant (Gtp) binary format. The feed is distributed over Ip multicast with Tcp recovery services for gap fill.

### Transport

Udp multicast via the Lseg Group Ticker Plant (Gtp) framing for real-time delivery of sequenced binary messages with per-packet sequence numbers. Tcp for the Gtp retransmission and snapshot services for recovery of missed multicast messages.

### Key Characteristics

- **Turquoise Mtf** - Coverage of the Lse Turquoise venue
- **Gtp format** - Lseg Group Ticker Plant binary encoding
- **Multicast delivery** - Udp multicast with sequence numbers
- **Gap recovery** - Tcp retransmission and snapshot services
- **Binary encoded** - Compact fixed-width binary messages

