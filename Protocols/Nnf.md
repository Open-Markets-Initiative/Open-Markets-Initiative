## Nnf: Non-Neat Front End

Nse's order entry wire encoding for member front ends other than the exchange supplied Neat terminal, carried on the Interactive Virtual Circuit. Messages are C structure images with fixed width fields and no padding between members, prefaced by the forty byte Message Header whose leading Transaction Code selects the structure to apply to the remaining bytes and whose trailing Message Length frames the Tcp byte stream. Unlike the Binary encoding used by the tick by tick market data feeds, every multi byte field is big endian.

### Overview

The encoding is the direct memory image of the structures printed in the specification. Field widths follow the documented data types, one byte for a char, two for a short, four for a long, and eight for a long long or a double precision value. Only Unsigned Long is unsigned; every other integer is signed.

Byte order is big endian, described in the specification from the reader's point of view as a twiddling requirement for little endian hosts. Bit packed structures are printed twice, once as they would be declared on a little endian machine and once for a big endian machine, because a C compiler allocates bit fields from the opposite end of the storage unit on each. Both listings describe the same bytes on the wire.

Alphabetical data is upper cased and padded on the right with blanks rather than terminated with a null, in both directions.

Several logically integral fields, among them Sequence Number, Order Number and Nnf Field, are declared as Double and are therefore genuine Ieee 754 values on the wire rather than integers.

The Broadcast Circuit is a separate encoding. It prefaces messages with Bcast Header rather than Message Header, packs several packets into one datagram behind a Net Id and packet count, and may compress each packed packet with Lzo. Only Unsigned Long and Byte appear there and not here.

### Transport

Interactive virtual circuit carrying request messages, their responses, and unsolicited messages such as trade confirmations, bidirectionally between the front end and the host.

