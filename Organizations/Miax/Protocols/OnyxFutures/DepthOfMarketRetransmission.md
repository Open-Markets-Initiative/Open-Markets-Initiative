## OnyxFutures Depth Of Market Retransmission: Depth Of Market Retransmission

Recovery interface for the Miax Futures Onyx Depth of Market feed, offering both a gap fill service that replays a requested range of sequenced packets and a last value refresh service that returns the current state of instrument definitions, trading status, system state and the full order book.

### Overview

Firms log in to the retransmission interface with a requested sequence number of zero, then choose one of two recovery services. The gap fill service uses the SesM Retransmission Request to replay an explicit range of sequenced packets from the live feed. The last value refresh service instead returns current state, which is how a firm that joined late rebuilds the book without replaying the whole session.

A refresh is driven by unsequenced data packets. The firm sends a refresh request naming one of four categories: instrument definitions, instrument trading status, system state, or order book. The exchange answers with a series of refresh responses, each carrying a sequence number followed by one ordinary Depth of Market application message, and closes with an end of refresh notification echoing the requested category.

The order book refresh is ordered rather than arbitrary. Every response carries the same sequence number, the last on the live feed when the request arrived, and the same timestamp. The exchange sends the latest system state, then for each simple and complex instrument its latest definition and trading status, then every add order message needed to rebuild that instrument's book. For the other three categories the sequence number in each response is the original one from the live feed, so a firm can arbitrate refresh against live data by taking the higher sequence number.

### Transport

Tcp via the SesM session management protocol, carrying replayed Depth of Market application messages in sequenced data packets for gap fill and in unsequenced data packets for last value refresh.

