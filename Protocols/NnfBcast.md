## NnfBcast: Non-Neat Front End Broadcast

Nse's broadcast wire encoding for member front ends other than the exchange supplied Neat terminal, carried one way on the Broadcast Circuit. Messages are the same big endian C structure images as the interactive Nnf encoding, but the framing differs: several packets are sequentially packed into one datagram behind a Net Id and a packet count, each packed packet may be compressed with Lzo, and each carries an eight byte prefix before a forty byte Bcast Header that replaces the interactive Message Header.

### Overview

A datagram opens with Net Id and a packet count, then that many packets are packed in Fifo order. Each packed packet begins with a two byte compression length. Zero means the data that follows is uncompressed; a non zero value is the length of an Lzo compressed block that must be inflated before it can be read. A single datagram may mix compressed and uncompressed packets.

Only nine transaction codes are ever compressed: 7200 Market By Order and Mbp, 7201 Market Watch, 7202 Ticker, 7208 Only Mbp, 7220 Limit Price Protection Ranges, and the enhanced forms 17201, 17202, 17208 and 17211.

Inside the broadcast data, once inflated where necessary, the first eight bytes precede the header and are skipped. The first of those eight carries the market type, where the value 2 denotes Futures and Options. The Bcast Header begins at the ninth byte.

Bcast Header is forty bytes like the interactive Message Header but lays its fields out differently. Transaction Code sits at offset ten rather than zero, a broadcast sequence number occupies offsets fourteen to seventeen, and only Message Length at offset thirty eight is common to both.

The type vocabulary is the interactive one plus two additions that appear only here: Unsigned Long, used by the enhanced ticker for Open Interest and its day high and low, and Byte, used once for the eight byte Filler2 padding in Bcast Header.

### Transport

Broadcast circuit carrying market data one way from the host to every front end.

