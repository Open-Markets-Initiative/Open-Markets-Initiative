## Mits: MITS Exchange System

Little endian binary encoding of the MITS Exchange System interface, framing each message in a four byte transport header and a twenty nine byte message header, with Pascal strings and gzip compressed downloads.

### Overview

Every message starts with a transport header, a 255 byte followed by the message length low and high bytes and their exclusive or, then a message header carrying a per socket sequence number, the user name, a user number, the time and the message type. The same message type can mean a request from the user and a reply from the exchange.

Integers and floating point values are in Intel byte order. Strings are Pascal strings: a length byte, then the characters, always taking the defined length on the wire. Dates are three integers and times four bytes of hours, minutes, seconds and zero.

Downloads and subscription replies are gzip compressed behind a four byte uncompressed length, and a compressed buffer longer than 5000 bytes is split across messages, the last part flagged in a sub header, so the parts are joined before the whole is decompressed.

### Transport

A Tcp connection per user, on which the exchange sends a session key challenge, the user logs in, and both sides exchange heartbeats when nothing else has been sent for 45 seconds.

### Key Characteristics

- **Checked length header** - The transport header repeats the length as the exclusive or of its two bytes
- **Pascal strings** - A length byte, then the characters, padded to the defined length
- **Chunked gzip** - Compressed buffers are split into 5000 byte sections, joined then decompressed

