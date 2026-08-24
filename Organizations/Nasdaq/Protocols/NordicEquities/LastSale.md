## NordicEquities Last Sale: Nasdaq Nordic Trade Report Feed

Post trade publication feed carrying on exchange and over the counter trade reports for the Nasdaq Nordic equities markets.

### Overview

Nordic Equity Last Sale is the trade report feed for the Nasdaq Nordic cash equity markets. It publishes on exchange executions, over the counter and systematic internaliser trades, and the adjusted closing price disseminated for every active symbol at the start of each trading day.

The message set is shaped by the Esma MiFid II post trade publication requirements, so trades carry execution and agreement dates and times, market model typology trade flags, venue of execution and notional amount. Over the counter reports express price, quantity and notional as integers whose decimal places are given by a companion fraction field.

### Transport

Udp multicast framed by Mold Udp 64 carrying a session identifier, a sequence number for the first message in the packet and a count of the message blocks that follow.

### Key Characteristics

- **Trade reporting** - On exchange, over the counter and systematic internaliser trades
- **MiFid II post trade** - Publication fields prescribed by the Esma post trade transparency regime
- **Adjusted close** - Previous day closing price adjusted for corporate actions
- **Mold Udp 64** - Udp multicast framing with sequenced message blocks

