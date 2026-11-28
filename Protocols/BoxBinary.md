## BoxBinary: BOX Binary Market Data

Little endian binary encoding of the BOX Binary Market Data Feed: blocks of length-prefixed messages behind a 32 byte block header that carries a nanosecond reference timestamp and the sequence number of the first message.

### Overview

Every message travels inside a binary block. The 32 byte block header gives the block size, the number of messages, a bit field naming the message kinds present, the line, a reference timestamp in nanoseconds since the Unix epoch and the sequence number of the first message; later messages are numbered implicitly.

Each message starts with an 8 byte header: its length, its type and a nanosecond offset from the block's reference timestamp. Prices are little endian integers with implied decimals, four on the long messages and two on the short ones.

### Transport

Multicast lines (Top of Book, Market Depth, Complex, Auction) on redundant feeds A and B, one binary block per datagram. Retransmission and snapshot service per trading slice, carrying the same binary blocks over a stream.

### Key Characteristics

- **Binary blocks** - A block header and the length-prefixed messages it counts
- **Reference timestamp** - Message time is the block reference time plus a per message offset
- **Long and short messages** - Compact two decimal prices for options, signed four decimal prices for complex instruments

