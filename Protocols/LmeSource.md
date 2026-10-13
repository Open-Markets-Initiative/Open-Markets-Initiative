## LmeSource: LMEsource

Fixed layout little endian binary encoding of the London Metal Exchange market data feed. A multicast packet is a sixteen byte packet header followed by the number of complete messages the header states, laid out one after another with no padding. Every message is length prefixed and self describing: its first field is its own size inclusive of that field, and its second field is its type. Prices are signed 64 bit integers scaled to six implied decimal places, timestamps are unsigned 64 bit UTC nanoseconds since epoch provided to microsecond precision, and character fields are left aligned ASCII padded with spaces. Each integer width carries a reserved sentinel that represents null rather than a value.

### Overview

A Heartbeat is not a message type but a packet: a packet header with Msg Count set to zero and no body. It does not carry a sequence number and does not advance the channel, so Seq Num repeats the sequence number of the previous message sent on that channel.

Null is carried in band as a per width sentinel rather than as an absence or a flag: 0x80 for Int8, 0x8000 0000 for Int32, 0x8000 0000 0000 0000 for Int64, and the all bits set value for each unsigned width. A consumer that treats these as ordinary values reads a large negative or a maximum quantity where the exchange means nothing at all.

Scaling is fixed by the field rather than carried on the wire. Prices use six implied decimal places, and the leg ratio of a strategy definition uses three, so a consumer must know the field to read the number.

Msg Size counts itself and the message type, so the body that follows the four byte message header is four bytes shorter than the size the message states.

### Transport

Multicast delivery on dual channels per commercial package, each real time channel paired with a refresh channel that republishes the current market image. A dedicated channel carries the Disaster Recovery Signal and otherwise only heartbeats. Retransmission service, authenticated by Logon and driven by Retransmission Request and Retransmission Response, replaying a stated sequence range of a named multicast channel.

### Key Characteristics

- **Little endian** - Every integer field is transmitted least significant byte first
- **Length prefixed messages** - A two byte self inclusive message size and a two byte message type precede every body
- **Counted packets** - The packet header states how many complete messages follow, and a message is never fragmented across packets
- **Sentinel nulls** - Each integer width reserves one value to mean null
- **Implied decimals** - Prices scale by six decimal places and strategy leg ratios by three, fixed by the field rather than stated on the wire
- **Counted repeating groups** - Aggregate book entries, strategy legs and trade leg records repeat behind a count field in the fixed part of the message
- **Paired refresh channels** - Every real time channel has a refresh channel that republishes the current image, ended by Refresh Complete

