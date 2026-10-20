## BmeEquities Full Depth: BME Equities Full Depth

The multicast full depth market information feed of the BME equities environment, which section 2.2.2 of the binary interface specifications calls the best coverage of market data during the session and the recommended way to obtain it. It publishes every active order rather than a limited number of top of book levels, except during auctions where only top of book is supplied, together with reference data, matched trades, session status and instrument status. A client builds the market image from the orders it receives and aggregates its own daily statistics. The feed carries twenty messages, the sixteen market information messages section 5.2 marks for the full depth feed and the four session level messages section 5.4 states the Udp feeds also carry.

### Overview

There is no packet header. Section 2.1 states that every feed is a series of sequenced messages and that the first three fields of any published message are its length including those two bytes, its one byte type and a four byte sequence number, so a datagram holds whole messages to its end and a listener detects loss by finding a gap in the sequence.

Heartbeat and Network Status repeat the sequence number of the last message sent rather than consuming one of their own, so they do not count as gaps. Neither can be replayed or recovered.

One document describes three wire layouts. Section 1.4.1 marks each field of each message with the environments that send it, Fixed Income, Equities and Derivatives, and states that a field not applicable to an environment is not sent at all, so a message is a different length in each. This specification carries the Equities subset.

Four of the twelve data types of section 1.4 are integers carrying an implicit scale: prices and volumes divide by ten to the sixth, monetary amounts and rates by ten to the fourth. Nothing on the wire states the scale, so a consumer applies the one its type names.

Section 5.3.2 states that an aggressive order is not published when it arrives if its price could match. If it is not fully filled it is published after the execution, so a client building the order book from order confirmations alone can ignore what the trade messages say about the pending volume of orders it has not seen.

### Transport

Multicast channels published as a redundant pair, A and B, a client reading both and taking the first copy of each sequence number to arrive. A single environment may publish separate feeds for different sets of symbols, and the messages that apply to all sets, Trading Session Status and News, are forwarded through every feed. The Replay server, which resends a requested range of packet sequence numbers a listener lost from both multicast channels, and the Recovery server, which sends a snapshot of the current market state to a client connecting late. Both are addressed by the session level messages of this specification and both fill silence with Heartbeats.

### Key Characteristics

- **Little endian** - Section 3.4.1 states that all numeric values are sent as little endian encoded integers
- **No packet header** - A datagram is a series of self describing messages, each stating its own length
- **Length prefixed messages** - Each message opens with a two byte size that counts its own two bytes, then a one byte type and a four byte sequence number
- **Implicit decimals** - Prices and volumes carry six decimal places, monetary amounts and rates four, stated by the data type rather than by the wire
- **Per environment message layouts** - One document serves three environments, each field marked with the environments that send it
- **Redundant channels** - Every feed is published on a channel pair, with a Replay and a Recovery server over Tcp behind it
- **Full order book** - Every active order is published, not an aggregated number of top of book levels

