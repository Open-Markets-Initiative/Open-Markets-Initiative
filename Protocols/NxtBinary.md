## NxtBinary: Nextrade native fixed-width Udp multicast market data

Binary is the native fixed-width market data encoding Nextrade publishes alongside the Ascii encoding, carrying the same records in a narrower form. Each Udp multicast datagram carries one record: 2 bytes Data Category, 3 bytes Information Category, then the payload with every numeric written as a native machine value and every character field left as Ascii text of the width it occupies in the Ascii encoding. The record ends with a 4-byte integer end keyword holding the message length, where the Ascii encoding writes a single 0xFF byte. Byte order is little endian and numeric fields are signed, confirmed directly by Nextrade; neither is stated in the English or the Korean edition of the specification.

### Overview

The Binary encoding exists to cut bandwidth: the same quote record that occupies 590 bytes in Ascii occupies 421 bytes here, because an 11-byte Ascii price becomes an 8-byte machine value and a 12-byte Ascii volume becomes 8 bytes. Message content, TR-CODE dispatch and field order are identical between the two encodings, so a consumer can switch encoding without re-mapping fields.

Byte order, signedness and floating point representation are documented nowhere in the specification. Nextrade confirmed directly that the feed is little endian and that numeric fields are signed, so integers are modelled as little endian two's complement. Floating point is IEEE 754 binary64 at 8 bytes and binary128 at 16 bytes, read from the workbook naming its own types double and __float128 — the latter a GCC x86-64 ABI spelling that appears verbatim in both the English and Korean editions.

Character fields are not converted. A 12-byte ISIN code, a 2-byte Board ID and a 12-byte HHMMSSuuuuuu processing time all occupy the same bytes and hold the same Ascii text in both encodings, which is why the Binary records are shorter but not proportionally so.

### Transport

Records are disseminated as native fixed-width Udp multicast datagrams, one message per datagram. The first 5 bytes remain Ascii and form the TR-CODE that discriminates the message type. The final 4 bytes are an integer end keyword carrying the message length.

### Key Characteristics

- **Native numerics** - Integers at 4 and 8 bytes, IEEE binary64 at 8 bytes and IEEE binary128 at 16 bytes, in place of Ascii digit runs
- **Ascii character fields** - Character fields keep Ascii text and the same width they occupy in the Ascii encoding
- **Ascii TR-CODE dispatch** - The leading 5-byte TR-CODE stays Ascii, so dispatch is identical to the Ascii encoding
- **4-byte end keyword** - Records end with a 4-byte integer carrying the message length rather than a single 0xFF sentinel
- **Little endian signed numerics** - Little endian byte order and signed integers, confirmed by Nextrade rather than stated in the specification

