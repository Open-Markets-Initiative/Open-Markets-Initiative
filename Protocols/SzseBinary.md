## SzseBinary: Szse Binary Market Data Feed

Fixed layout big endian binary encoding of the Shenzhen Stock Exchange Market Data Gateway. Every message carries a four byte message type and a four byte body length, a body whose field layout is fixed per message type, and on a session connection a four byte trailing checksum. Prices, quantities and amounts are signed 64 bit integers scaled to a documented number of decimal places, timestamps are signed 64 bit integers holding a local YYYYMMDD-HH:MM:SS.sss wall clock reading, and character fields are space padded UTF-8. The same message set is published in tag value form by the companion STEP volume.

### Overview

The Szse Binary encoding is the binary volume of the Market Data Gateway interface specification. Field names, message types and message flow are shared with the STEP volume, which carries the same content as FIX style tag value pairs, so the two volumes are mutual references and a reader of one can follow the other.

Field widths are not given in the message tables. Each message table lists field names and meanings, and the data dictionary in the final chapter maps every field name to a binary type, either directly or through a named business type such as Price, Qty, Amt, SeqNum or LocalTimeStamp. A reader must join the two tables to recover the wire layout.

Scaling is carried by the business type rather than by the field. Price is a signed 64 bit integer with four decimal places, Qty carries two, and Amt carries four, while MDEntryPx is declared separately as a signed 64 bit integer with six decimal places. A consumer that applies the Price scale to MDEntryPx is wrong by two orders of magnitude.

The encoding is designed for forward compatibility. A subscriber is required to tolerate new channels, new message types, new market data categories, new market data entry types, new security switch types, and new fields appended to the tail of an existing message, without an upgrade.

### Transport

Point to point session to the Market Data Gateway, one connection per port, with a real time port and a re-transmission port. Logon, Logout and Heartbeat manage the session, and each application message carries the mod 256 checksum of its header and body in a trailing Checksum field. Multicast delivery through the Market Data Distribution Protocol, which packs several complete application messages into one packet behind a length table and checks the whole packet with Adler32. The per message Checksum of the session encoding is omitted under multicast.

### Key Characteristics

- **Big endian** - Every integer field is transmitted in network byte order
- **Length prefixed messages** - A four byte message type and four byte body length precede every body
- **Scaled integers** - Prices, quantities and amounts are signed 64 bit integers with a scale fixed by the business type
- **Wall clock timestamps** - Timestamps are integers holding a readable local YYYYMMDD-HH:MM:SS.sss value, not an epoch offset
- **Repeating groups** - Counted groups carry market data entries, security switches and trading phase subdivisions, nested one level for the orders disclosed at a price level
- **Utf-8 text** - Character fields are fixed width, space padded on the right and may carry Chinese characters
- **Tail extensible** - New fields may be appended to the tail of a message and new categories added without a subscriber upgrade

