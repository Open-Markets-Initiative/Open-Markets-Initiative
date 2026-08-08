## Lse Level2Incremental: Level 2 Incremental

Level 2 incremental order by order service publishing add, modify and delete instructions for London Stock Exchange instruments over the Group Ticker Plant.

### Overview

Level 2 Incremental is the Lseg Group Ticker Plant order by order service for London Stock Exchange. Rather than republishing the book, it disseminates Add Order Incremental, Order Modify and Order Delete instructions that a subscriber applies to a retrospective order book, each carrying both the dissemination timestamp and the transaction time reported by the upstream trading system.

The service additionally carries the Trade Summary message, which reports the aggregate result of a matching engine event including total and hidden executed quantity, the far price, the side of the resting orders that triggered the event and the best bid and offer at execution completion.

### Transport

Udp multicast using the Lseg Group Ticker Plant unit header framing for real time delivery of sequenced binary messages. Tcp for the Group Ticker Plant replay and recovery services used to recover missed multicast messages.

### Key Characteristics

- **Order by order** - Add, modify and delete instructions maintain a retrospective order book
- **Transaction time** - Instructions carry the upstream execution timestamp alongside the dissemination time
- **Priority flag** - Order Modify signals whether the order retained or lost time priority
- **Trade summary** - Multi and single fill trade events are summarised with resting book context

