## Aspen: Imperative Intelligent Cross binary market data encoding

Little-endian binary market data encoding used by the Imperative Intelligent Cross market data feed. Wire framing is a packet header (Market Day Identifier, Feed Identifier, Sequence, Count) followed by concatenated fixed-width messages carrying ASPEN book events — order add, update, partial cancel, cancel all, executed — plus trades, trade breaks, symbol information/state, and market events.

### Overview

Aspen is the binary encoding of the Intelligent Cross market data feed, named for the venue's ASPEN order books (Adverse Selection Protection Engine) whose visible orders, resting orders, and executions the feed publishes. Messages are fixed-width and little-endian, framed by a compact packet header carrying the market day, feed identifier, sequence number, and message count.

### Transport

Udp multicast delivery of sequenced binary packets; per-packet sequence numbers and message counts support gap detection across redundant feeds.

