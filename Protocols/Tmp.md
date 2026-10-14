## Tmp: Taifex Message Protocol

Fixed layout big endian binary encoding of the Taiwan Futures Exchange Tcp/Ip order and execution report network. Every message carries a seventeen byte common message header holding a message length, a message sequence number, a message time, a one byte message code and the futures commission merchant and session identifiers, a body whose field layout is fixed per message code, and a one byte trailing check sum that is the sum of every preceding byte modulo 256. Integers are two, four or eight byte signed or unsigned values in network byte order, prices are plain integers whose decimal scale is the Decimal_Locator of the product definition file rather than a property of the field, times are a Unix epoch second count beside a millisecond or nanosecond fraction, and character fields are fixed width Ascii. The same order entry service is published in tag value form by the companion Fix volume.

### Overview

Section 2.1 names the message codes by their layer: a code starting with the letter L is a Link Subsystem message, which communicates in back-and-forth mode, and a code starting with R is a Trading Subsystem message, which communicates asynchronously so that the next message may be sent without waiting for a response. A field whose definition matches a Fix tag is named in mixed case and every other field name is compatible with C, all in lower case.

The message length counts neither its own two bytes nor the trailing check sum. Section 2.1.1 defines it as the total number of bytes behind the msg_length field up to before the CheckSum field, so a frame on the wire is the message length plus three, and a body of variable length is stated as the message length less the fifteen header bytes that follow msg_length and less the fixed fields of its own body.

A product identifier is carried either as a number or as text, and the message states which by a discriminator of its own rather than by its message code. The numeric and text forms of a pair occupy the same width, twenty bytes for the short pair and forty for the long pair, so the choice changes the layout of the field without changing the length of the message. The numeric identifiers are assigned per session and are not necessarily carried over from the previous day, so the product definition file must be downloaded each day before connecting.

Message sequence numbers are maintained independently by each side. Each new order, cancel or change order message is assigned a sequence number as a unique identification code, each side is responsible for the sequence of the messages it sends and for monitoring the sequence of those it receives, and a gap returns the session to the wake up call that opens the Link Subsystem.

The expanded message header assigns additional subcategories to a message code. Where a message carries it, the expanded MessageType selects between the layouts the message may take, and so acts as a second level of dispatch beneath the one byte message code of the common header.

### Transport

Asynchronous point to point session over Tcp/Ip, whose address is resolved through the Taifex domain name system server. A session is established by the Link Subsystem, whose messages are named by a code beginning with L, and then carries Trading Subsystem messages, whose codes begin with R, in both directions without waiting for a response. The application system code of the request logon selects which of the order and execution report, clearing member and drop copy lines the session joins.

### Key Characteristics

- **Big endian** - Every multi byte integer is transmitted in network byte order
- **Length prefixed messages** - A two byte message length opens the common message header of every message
- **Check summed messages** - Every message ends in the sum of its preceding bytes modulo 256, and a check sum error returns the session to the wake up call
- **Externally scaled prices** - Prices are plain integers whose number of decimal digits is the Decimal_Locator of the product definition file
- **Epoch second times** - A message time is a Unix epoch second count beside a millisecond fraction, with a nanosecond fraction in the expanded header
- **Numeric or text product identifiers** - A product may be named by an assigned number or by its text symbol, selected per message by a discriminator and occupying the same width either way
- **Asynchronous both ways** - Trading Subsystem messages flow in both directions on one connection without waiting for a response

