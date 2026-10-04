## Gfx: Tmx Global Fx datagram encoding

Tmx's datagram encoding for the Global Fx reference price feed. Each datagram opens with a one byte type and carries a fixed portion followed by a size tier repeated as many times as the datagram says, every field at a stated byte offset. Integers wider than a byte are big endian, which sets it apart from the other Tmx binary encodings.

### Overview

Global Fx is the encoding Tmx states for its foreign exchange reference price feed. It names no template or schema on the wire, so a decoder maps each datagram onto the layout the specification publishes, selected by the single character the datagram opens with.

Prices are carried as a signed mantissa with an exponent field beside it, so each repeat states its own precision rather than taking a scale from the field definition. Character fields are fixed width and right padded with space, and every integer wider than one byte is big endian.

### Transport

One datagram per packet, refreshed periodically per currency pair so a subscriber can tell stale prices from quiet ones.

### Key Characteristics

- **Offset stated** - Every field carries the byte offset the document states for it
- **Big endian** - Integers wider than a byte are big endian
- **Exponent scaled** - Each price carries its own exponent rather than an implied scale
- **Repeating tier** - A fixed portion followed by a group repeated as a count field states
- **Datagram framed** - One datagram per Udp packet, with no session or sequencing layer of its own

