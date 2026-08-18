## Lse Level2Mbp: Level 2 MBP

Level 2 market by price snapshot service publishing aggregated price points for London Stock Exchange instruments over the Group Ticker Plant.

### Overview

Level 2 MBP is the Lseg Group Ticker Plant market by price snapshot service for London Stock Exchange. Displayed liquidity is aggregated into price points, the first price point on a given side arriving as an Add Order MBP message carrying the full instrument and side context, with subsequent price points arriving as the abbreviated Add Order Short MBP message.

Each price point reports a Splits count giving the number of orders resting at that price, and the Add Order MBP message reports the total Depth for the side. The service is available on the real time multicast channels and through the Tcp replay and recovery services.

### Transport

Udp multicast using the Lseg Group Ticker Plant unit header framing for real time delivery of sequenced binary messages. Tcp for the Group Ticker Plant replay and recovery services used to recover missed multicast messages.

### Key Characteristics

- **Market by price** - Orders are aggregated into price points rather than published individually
- **Split counts** - Each price point reports the number of orders resting at that price
- **Snapshot oriented** - Add Order MBP and Add Order Short MBP rebuild a side of the book in order

