## TradeEcho Level2Incremental: Level 2 Incremental

Level 2 incremental order by order feed published via the Trade Echo service over Udp multicast using Group Ticker Plant framing, carrying Systematic Internaliser quotes on the pre trade service line.

### Overview

Level 2 Incremental is the real time Trade Echo feed carrying Systematic Internaliser quotes published on behalf of investment firms. Each SI Quote message names the submitting participant, the side, price and displayed size, so a subscriber maintains a quote book per instrument from the sequenced event stream.

Quotes are removed by Delete Order and the whole book for an instrument is dropped by Order Book Clear, which is published only in a failover scenario. Order identifiers may repeat within a trading day after a quote is cancelled, and are reused across days, so quotes on different days are distinct.

### Transport

Udp multicast using the Lseg Group Ticker Plant (Gtp) unit header framing, with a sequence number on the first payload message of each packet for gap detection.

### Key Characteristics

- **Order by order** - Individual quote add and delete events rather than aggregated price levels
- **Participant attributed** - Each quote names the trading participant that submitted it
- **Pre trade transparency** - Publishes Systematic Internaliser firm quotes under MiFID II pre trade obligations
- **Multicast delivery** - Udp multicast with sequence numbers and dual feed arbitration

