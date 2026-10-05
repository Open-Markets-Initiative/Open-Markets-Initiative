## NxtAscii: Nextrade Ascii fixed-width Udp multicast market data

Ascii is the printable fixed-width market data encoding Nextrade uses to disseminate its Korean alternative trading system data. Each Udp multicast datagram carries one record: 2 bytes Data Category, 3 bytes Information Category, a fixed-width Ascii payload and a single 0xFF end keyword byte. Numeric fields are right-justified zero-filled digit runs; fields declaring decimal places write the decimal point on the wire. Prices are nine significant digits preceded by a sign byte and an unused byte, both always set to zero.

### Overview

Nextrade mirrors the Koscom Exture TR-CODE conventions so that member firms consuming Korea Exchange market data can decode Nextrade data with the same field vocabulary. Several batch fields exist purely to match the Korea Exchange message layout and are never populated by Nextrade; the specification marks these for synchronization only.

Message dispatch is by TR-CODE, formed by concatenating a 2-character Data Category naming the message family with a 3-character Information Category naming the market or product variant. The Information Category distinguishes KOSPI stock, KOSDAQ stock and exchange traded product streams, so one message layout serves several markets under different codes.

The same message content is offered at four bandwidth flavors that differ only in how many quote levels they carry and which messages they include. Common carries filtered quotes at ten levels, while the 10, 5 and 3 Level products carry unfiltered quotes at the stated depth. The level flavors reuse one TR-CODE per family, so a given port carries exactly one depth variant.

### Transport

Records are disseminated as Ascii fixed-width Udp multicast datagrams, one message per datagram. The first 5 Ascii bytes form the TR-CODE that discriminates the message type, and the final byte is a 0xFF end keyword. Retransmission is served over separate Tcp recovery ports.

### Key Characteristics

- **Ascii fixed-width** - Every field is a fixed byte width of printable Ascii; numeric fields are right-justified zero-filled digit runs
- **Two-level TR-CODE dispatch** - 5-byte TR-CODE = 2-byte Data Category naming the family + 3-byte Information Category naming the market or product
- **Udp multicast** - One message per datagram; multicast groups and ports partition streams by subscription product and bandwidth flavor
- **0xFF end keyword** - Every record ends with a single 0xFF byte marking the end of the message
- **Written decimal point** - Fields declaring decimal places write the point on the wire, consuming one byte of the declared width

