## Fast: FIX Adapted for STreaming

Template driven binary encoding of Fix messages for market data, maintained by the FIX Trading Community's Market Data Optimization Working Group, which removes field tags and redundant values from the wire by stating each message's layout in a template the sender and receiver both hold.

### Overview

Fast (FIX Adapted for STreaming) is a FIX Trading Community standard for encoding Fix messages compactly, developed for market data by the Market Data Optimization Working Group. The FIX Trading Community publishes the Fast Specification version 1.1 and the Fast Extension version 1.2, which proposes extensions to Fast 1.1.

A message is decoded by its template. Every message opens with a presence map, a set of bits saying which of the template's fields that need one are present, followed by the template identifier, which names the template stating the message's fields, their order, their types and their operators. Because the template fixes the order, a field is known by its position and its Fix tag is not sent. Venues publish their templates as Xml files.

Most fields are stop bit encoded: each byte carries seven bits of the value and a stop bit that marks the field's last byte, so a small number takes one byte and no field needs a length. Field operators such as constant, default, copy, increment and delta remove values the receiver can supply itself, from the template or from the previous value held in a dictionary. That makes the decoder stateful, and a venue states when its dictionaries reset.

A Fast decoder yields field values rather than Fix messages, so a receiver that wants Fix composes the message itself from the decoded fields. Version 1.2 adds type definitions that a template refers to by name, enumerations, sets of values sent together as bits, and a timestamp type counting time units since an epoch.

### Transport

Carried in Udp multicast datagrams, each holding one or more Fast encoded messages. Eurex T7 opens every datagram with a packet header and a reset message, so a datagram decodes on its own without the ones before it.

### Key Characteristics

- **Template driven** - Xml templates state each message's fields, order, types and operators, and the template identifier on the wire selects one
- **Presence map** - Bits at the head of each message say which of the template's optional or operator fields are present
- **Stop bit encoding** - Each byte holds seven data bits and a stop bit marking the end of the field, so fields need no length or delimiter
- **Field operators** - Constant, default, copy, increment and delta operators leave out values the receiver can derive
- **Stateful decoding** - Operators read previous values from dictionaries, so a decoder must see messages in order from the last reset
- **Fix semantics** - Templates name the Fix tag and field each value stands for, so decoded messages carry Fix meaning

