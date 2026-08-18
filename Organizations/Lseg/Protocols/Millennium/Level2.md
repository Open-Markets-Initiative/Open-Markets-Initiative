## Millennium Level2: Level 2

Level 2 order by order feed publishing add, modify, execute and delete events for securities traded on the Lseg Millennium Exchange platform.

### Overview

Millennium Level 2 is the order by order market data feed for the Lseg Millennium Exchange trading platform, delivered in the Millennium Itch (Mitch) binary encoding. Subscribers reconstruct the full order book from a stream of individual order events rather than aggregated price levels.

The feed was superseded by the Group Ticker Plant (Gtp) architecture, which consolidated the Mitch message semantics into a single multi venue protocol across the Lseg markets. This specification is retained for reference against historic captures.

### Transport

Udp multicast carrying Mitch binary messages under the Millennium unit header framing, with per-packet sequence numbers for gap detection and two identically sequenced feeds for arbitration. Tcp to the Millennium replay and snapshot services for recovery of messages missed on the multicast feed and for initialising book state.

### Key Characteristics

- **Millennium Exchange** - Native Level 2 market data for the Lseg Millennium trading platform
- **Order by order** - Add, modify, execute and delete events for each individual order
- **Mitch encoded** - Millennium Itch fixed width binary messages
- **Superseded by Gtp** - Replaced by the consolidated Group Ticker Plant feed across Lseg venues

