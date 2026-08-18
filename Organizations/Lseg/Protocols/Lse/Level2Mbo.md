## Lse Level2Mbo: Level 2 MBO

Level 2 market by order snapshot service publishing individual displayed orders for London Stock Exchange instruments over the Group Ticker Plant.

### Overview

Level 2 MBO is the Lseg Group Ticker Plant market by order snapshot service for London Stock Exchange. Each displayed order is disseminated separately, the first order on a given side arriving as an Add Order message that carries the full instrument and side context, with subsequent orders on the same side arriving as the abbreviated Add Order Short message.

The Depth field on the Add Order message states the total number of orders being disseminated for that side, allowing a subscriber to know when a side of the book is complete. The service is available on the real time multicast channels and through the Tcp replay and recovery services.

### Transport

Udp multicast using the Lseg Group Ticker Plant unit header framing for real time delivery of sequenced binary messages. Tcp for the Group Ticker Plant replay and recovery services used to recover missed multicast messages.

### Key Characteristics

- **Market by order** - Every displayed order is published individually with its own identifier
- **Snapshot oriented** - Add Order and Add Order Short rebuild a side of the book in order
- **Participant attribution** - Orders carry the identity of the submitting trading participant

