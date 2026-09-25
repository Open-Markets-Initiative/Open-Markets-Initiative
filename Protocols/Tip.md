## Tip: Transaction Information Protocol

Nasdaq Genium Market Info Transaction Information Protocol, a tagged text market data format of semicolon separated tag and value pairs carried in sequenced session packets.

### Overview

TIP (Transaction Information Protocol) is a tagged text protocol. A message is a sequence of tag and value pairs separated by semicolons; a tag is zero or more upper case characters followed by one lower case character, and the value follows the tag directly. The first tag is always the message type and carries no value; the order of the remaining tags is not fixed.

Basic data messages provide reference data such as exchanges, markets and tradable instruments, each identified by a stable Id that real-time messages such as trades, order books and index updates reference. Special characters in values (the field, index and value delimiters) are escaped with a backslash, and clients are expected to ignore unrecognized messages and tags so that new versions remain compatible.

### Transport

TIP messages are carried in a Nasdaq session protocol over TCP: SoupBinTCP sequenced data packets at Borsa Istanbul, and Xmp framing on X-stream venues, which provide login, sequencing and recovery.

### Key Characteristics

- **Tagged text** - Semicolon separated tag and value pairs, UTF-8 encoded unless stated otherwise
- **Message type first** - The first tag names the message; the other tags may appear in any order
- **Escaped delimiters** - A backslash escapes the field, index and value delimiters inside values
- **Reference data model** - Basic data entities carry stable Ids that real-time messages reference
- **Forward compatible** - Clients ignore unrecognized messages and tags as new versions add them

