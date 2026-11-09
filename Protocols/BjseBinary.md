## BjseBinary: Bjse Binary Market Data Feed

Fixed layout big endian binary encoding of the market quotation gateway (BJQG) and the trading gateway (BJTG) shared by the Beijing Stock Exchange and the National Equities Exchange and Quotations. Every message carries a four byte message type and a four byte body length, a body whose field layout is fixed per message type, and on a session connection a four byte trailing checksum. Prices, quantities and amounts are signed 64 bit integers scaled to a documented number of decimal places, timestamps are signed 64 bit integers holding a local YYYYMMDDHHMMSSsss wall clock reading, and character fields are fixed width GB18030.

### Overview

The encoding follows the Shenzhen Stock Exchange binary market data design: the same message header and checksum, the same split of field names from field types, and FIX style field names. The message type numbers, the business types' decimal scales and the character set are its own.

Field widths are not given in the message tables. Each message table lists field names and meanings, and the data dictionary in the final chapter maps every field name to a binary type, either directly or through a named business type such as Price, Qty, Amt, SeqNum or LocalTimeStamp. A reader must join the two tables to recover the wire layout.

Scaling is carried by the business type rather than by the field. Price is a signed 64 bit integer with five decimal places, Qty carries three, and Amt carries three, while MDEntryPx is declared separately as a signed 64 bit integer with five. These scales differ from the Shenzhen encoding the format follows, so a parser shared between the two is wrong by an order of magnitude on every price.

An unused field is filled with spaces when it is a string and with 0 when it is a number. A numeric string such as a security code is padded on the left with spaces, every other string on the right.

### Transport

Point to point session to the market quotation gateway, which offers a real time port and a retransmission port, or to the trading gateway, which offers one trading port per platform; each port accepts one connection. Logon, Logout and Heartbeat manage the session, and every message carries the mod 256 checksum of its header and body in a trailing Checksum field. Multicast delivery through the Market Data Distribution Protocol, which packs several complete application messages into one packet, optionally behind a length table, and checks the whole packet with Adler32. The per message Checksum of the session encoding is omitted under multicast.

### Key Characteristics

- **Big endian** - Every integer field is transmitted in network byte order
- **Length prefixed messages** - A four byte message type and four byte body length precede every body
- **Scaled integers** - Prices, quantities and amounts are signed 64 bit integers with a scale fixed by the business type
- **Wall clock timestamps** - Timestamps are integers holding a readable local YYYYMMDDHHMMSSsss value, not an epoch offset
- **Repeating groups** - Counted groups carry channel statistics per market data category, market data entries, security switches, trading phase subdivisions and order entry platform partitions, nested one level for the orders disclosed at a price level
- **Gb18030 text** - Character fields are fixed width, space padded and may carry Chinese characters

