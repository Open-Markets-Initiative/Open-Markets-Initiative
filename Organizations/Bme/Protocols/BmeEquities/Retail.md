## BmeEquities Retail: BME Equities Retail Top Of Book

The multicast top of book market information feed of the equities environment on channels G and H, carrying one price level in place of the full depth feed's order by order prices. Its own price messages are Top-of-book Retail (0x91). It carries the reference data, the trades, the session and instrument status, the statistics and the request for quote messages that section 5.2 marks for the top of book feed, and not the order and quote pre-transparency messages, the order by order trade message or the Order Book Clear, which that table marks for the full depth feed alone. A client aggregates its own daily statistics, as it would on the full depth feed, but has no order book to build.

### Overview

Section 2.2.3 states that channels G and H are specific to the Retail Service and equivalent to channels C and D, but that Top-of-book Retail arrives in place of Top-of-book.

There is no packet header. Section 2.1 states that every feed is a series of sequenced messages and that the first three fields of any published message are its length including those two bytes, its one byte type and a four byte sequence number, so a datagram holds whole messages to its end and a listener detects loss by finding a gap in the sequence.

One document describes three wire layouts. Section 1.4.1 marks each field of each message with the environments that send it, Fixed Income, Equities and Derivatives, and states that a field not applicable to an environment is not sent at all, so a message is a different length in each. This specification carries the Equities subset.

Four of the twelve data types of section 1.4 are integers carrying an implicit scale: prices and volumes divide by ten to the sixth, monetary amounts and rates by ten to the fourth. Nothing on the wire states the scale, so a consumer applies the one its type names.

### Transport

Multicast channels published as a redundant pair, a client reading both and taking the first copy of each sequence number to arrive. A single environment may publish separate feeds for different sets of symbols, and the messages that apply to all sets, Trading Session Status and News, are forwarded through every feed. The Replay server, which resends a requested range of packet sequence numbers, and the Recovery server, which for a top of book feed sends the current market and security status, the matched trades and the current top of book rather than the orders in the books.

### Key Characteristics

- **Top of book prices** - one price level, not the order by order prices of the full depth feed
- **Little endian** - Section 3.4.1 states that all numeric values are sent as little endian encoded integers
- **No packet header** - A datagram is a series of self describing messages, each stating its own length
- **Per environment message layouts** - One document serves three environments, each field marked with the environments that send it
- **Redundant channels** - channels G and H, a pair carrying the same messages

