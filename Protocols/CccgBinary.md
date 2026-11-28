## CccgBinary: China Connect Central Gateway Binary

Binary encoding of the Hkex China Connect Central Gateway trading and drop copy interfaces: little endian messages framed by a start of message character and a length, whose body fields are selected by a presence bitmap in the header and closed by a CRC32C checksum.

### Overview

Every message is a header, a body and a trailer. The header ends with a 32 byte Body Fields Presence Map whose bits, counted from the most significant, name the body fields present in their order; each message numbers its own bit positions. A repeating block is a count followed by entries, each with its own two byte presence map, and blocks nest.

Alphanumeric fields are null terminated, fixed length or prefixed with a two byte length. Decimals are signed 64 bit integers with eight implied decimal places. The trailer is a CRC32C checksum over the header and body.

### Transport

Tcp session to the CCCG, located through a lookup service that returns the primary and secondary connection points.

### Key Characteristics

- **Presence map** - A header bitmap selects the body fields present, most significant bit first
- **Nested repeating blocks** - Counted blocks whose entries carry their own presence maps
- **CRC32C trailer** - Every message ends with a CRC32C checksum, polynomial 0x1EDC6F41

