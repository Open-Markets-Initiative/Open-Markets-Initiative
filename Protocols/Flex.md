## Flex: Japan Exchange Group arrowhead tag-stream binary encoding

Tag-stream binary wire format used by the Japan Exchange Group arrowhead platform. Variable length tags are framed by a one byte Tag Length followed by Tag Data, whose first byte identifies the message type. Numeric fields are big-endian binary and text fields are left-aligned ASCII padded with spaces.

### Overview

Flex defines only the byte-level framing of arrowhead market data tags. Each tag begins with a one byte Tag Length, allowing a parser to advance to the next tag without inspecting tag contents. Within the tag body, the first byte is the Tag Type discriminator that selects the per-message field layout defined by the protocol specification.

Per-message field layouts (which bytes mean which fields for each Tag Type) are not part of the encoding. They are described in the application protocol document, and the Flex encoding is reused across the multiple arrowhead application protocols (cash equities Market by Order, Market by Price, Trade feed, etc.).

Encoding-level concerns end at the tag boundary. Packet headers, sequencing, multicast group assignment, snapshot and retransmission semantics belong to the application protocol that carries Flex tags (see Jpx.Flex.Protocol).

### Key Characteristics

- **Tag-stream framing** - One byte Tag Length prefix followed by Tag Data, enabling skip-ahead parsing without decoding contents
- **One byte type discriminator** - First byte of every tag selects the per-message field layout defined by the application protocol
- **Big-endian numerics** - Multi-byte integer and price fields are encoded in network byte order
- **Left-aligned ASCII text** - Fixed-width text fields are left-aligned and space-padded
- **Schema independent** - Wire format carries no schema identifiers; per-tag layouts are defined entirely by the application protocol document

