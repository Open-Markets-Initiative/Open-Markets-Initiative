## Binary: Binary

Nse's plain binary wire encoding, used by the tick by tick market data feeds. Messages are C structure images with fixed width fields, little endian byte order, and no padding between members. There is no self describing template or schema on the wire, so a decoder must map each message onto the layout published in the specification, selected by the single byte message type that opens every message.

### Overview

The encoding is the direct memory image of the structures printed in the specification, compiled with one byte packing. Field widths follow the documented data types, one byte for a character, two for a short, four for an integer, and eight for a long or a double precision value.

Framing is minimal. A stream header carrying the message length, stream identifier, and sequence number precedes each message, and the message itself begins with a one byte type code that selects the structure to apply to the remaining bytes.

### Transport

Real time multicast delivery of sequenced market data messages. Recovery delivery of replayed messages in the same wire format.

