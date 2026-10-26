## Spectra Orders Log Incremental: SIMBA Spectra Orders Log Incremental

Real-time full order log of the Moex derivatives market, publishing every order book modification as it happens: order added, changed and deleted events, executions reported as trades, and the resulting best bid and offer published at the head of each transaction before the order events that caused it. An empty book message states that a side has been emptied. Broadcast as paired A and B multicast streams on separate groups, each packet carrying a market data packet header, an incremental packet header stating when matching began on the transaction, and one or more Sbe messages. A transaction too large for one datagram is fragmented across packets and marked in the header flags.

### Transport

Udp multicast, duplicated as an A and a B group so a subscriber can arbitrate the two against packet loss, with as many Sbe messages per datagram as the transaction needs and the Ethernet Mtu allows.

### Key Characteristics

- **Full order log** - Order-by-order add, change and delete events with executions reported separately
- **Best prices first** - A transaction opens with the resulting best bid and offer before the order events
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Transaction timing** - An incremental packet header states when matching began on the transaction
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration
- **Packet fragmentation** - A transaction larger than one datagram is split and marked in the header flags

