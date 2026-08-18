## Turquoise Level1Incremental: Level 1 Incremental

Level 1 Incremental top of book feed publishing best bid and offer updates, trades and statistics for instruments traded on the Lseg Turquoise Mtf.

### Overview

Level 1 Incremental is the Turquoise top of book service. The Top of Book message reports the consolidated best bid and offer for an instrument, republished on every change, so a subscriber maintains the touch without processing individual order events.

Alongside the quote stream the service carries the trade messages, the running and end of day statistics, and the reference and status messages shared by all Group Ticker Plant service lines. Gaps are recovered through the shared replay and recovery channels rather than a service specific one.

### Transport

Udp multicast using the Lseg Group Ticker Plant (Gtp) unit header framing, with per packet sequence numbers for gap detection and two identically sequenced feeds for arbitration.

### Key Characteristics

- **Top of book** - Consolidated best bid and offer rather than full depth
- **Incremental updates** - A new Top of Book message is published on each change to the touch
- **Trades and statistics** - Carries the trade stream together with running and snapshot statistics
- **Multicast delivery** - Udp multicast with sequence numbers and dual feed arbitration

