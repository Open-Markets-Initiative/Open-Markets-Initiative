## NomOptions Itto: Nasdaq Itch to Trade Options, the Nom order and quote depth feed

Full order and quote depth Itch feed for options traded on the Nasdaq Options Market, tracking the life of every order and quote and reporting trades, auction transactions and the opening net order imbalance.

### Overview

Itto is the depth of book market data feed for the Nasdaq Options Market (Nom). Its own specification calls it a direct data feed carrying full order and quote depth: a series of add, replace, cancel, delete and execute messages track the life of each order and quote, trade messages cover the matches and auction transactions the order messages do not already state, and Net Order Imbalance Indicator messages give the indicative clearing price before the opening auction. It is an outbound feed only and does not support order or quote entry. Delivery is over MoldUdp64 multicast with a SoupBinTcp Glimpse snapshot and retransmission service for recovery.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order and quote depth** - Full depth of book, a message per order and quote event
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Net order imbalance** - Indicative clearing price before the opening auction

