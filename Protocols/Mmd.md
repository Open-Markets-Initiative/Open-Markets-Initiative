## Mmd: Multicast Market Data Feed

Proprietary binary market data protocol of the Canadian Securities Exchange, carrying order-by-order depth, trades and best quotes for the CSE and CSE2 books. Fixed-position big-endian fields behind a seven byte block header that counts the messages it carries, with a two byte sub header per message.

### Overview

The feed has two data types and no others: Alphanumeric fields are left-justified ASCII padded right with spaces, and Integer fields are unsigned big-endian binary of 1, 2, 4 or 8 bytes. Prices are Integers carrying four implied decimal places, so a wire value of 123400 is a price of 12.34.

Time is carried two ways. A Time message states seconds since midnight Eastern of the first day of the system cycle, and every subsequent message's Timestamp field is nanoseconds since that last Time message. Alongside it most messages carry an Exchange Timestamp of milliseconds since the Unix epoch, which the documents call the official exchange time.

Messages are not fixed length by contract. The exchange reserves the right to append fields to any message, instructing clients to dispatch on the Message Type and ignore trailing bytes beyond what they expect, so the sub header length rather than a table total bounds each message.

### Transport

Udp multicast carries the real-time feed, combining as many messages into one datagram as will fit behind a single block header that states the sequence number of the first message and how many follow; each subsequent message is implicitly numbered one higher. A Tcp session carries retransmission and spin, reached after a login and kept alive by a heartbeat each minute. Retransmission replays a requested sequence range in the same framing the multicast feed used; spin returns a full order book snapshot whose messages are sequenced but may arrive out of order.

### Key Characteristics

- **Market-by-order granularity** - Add, execute, replace and delete events carrying an eighteen byte order number
- **Binary encoding** - Unsigned big-endian integers and space-padded ascii at fixed positions
- **Block framing** - One seven byte header per datagram counting the messages behind it
- **Implied sequencing** - The header numbers only the first message; the rest advance by one
- **Forward compatible messages** - Trailing fields may be appended, so clients ignore bytes past their own expectation
- **Tcp retransmission** - A sequence range replayed over a logged-in Tcp socket in multicast framing
- **Tcp spin snapshot** - A full book snapshot for a client that has lost its book, bracketed by spin responses

