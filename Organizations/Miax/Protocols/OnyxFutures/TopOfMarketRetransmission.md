## OnyxFutures Top Of Market Retransmission: Top Of Market Retransmission

Recovery interface for the Miax Futures Onyx Top of Market feed, offering both a gap fill service that replays a requested range of sequenced packets and a last value refresh service that returns the current state of instrument definitions, trading status, system state and top of market.

### Overview

Firms log in to the retransmission interface with a requested sequence number of zero, then choose one of two recovery services. The gap fill service uses the SesM Retransmission Request to replay an explicit range of sequenced packets from the live feed. The last value refresh service instead returns current state, which is faster for a firm that joined late and does not need the intervening history.

A refresh is driven by unsequenced data packets. The firm sends a refresh request naming one of four categories: instrument definitions, instrument trading status, system state, or top of market. The exchange answers with a series of refresh responses, each carrying the original live feed sequence number followed by one ordinary Top of Market application message, and closes with an end of refresh notification echoing the requested category. The exchange then sends a GoodBye packet and disconnects.

### Transport

Tcp via the SesM session management protocol, carrying replayed Top of Market application messages in sequenced data packets for gap fill and in unsequenced data packets for last value refresh.

