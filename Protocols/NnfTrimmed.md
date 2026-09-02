## NnfTrimmed: Non-Neat Front End Trimmed

Nse's trimmed order entry wire encoding, defined by the Trimmed Structures section of the specification and used both by Corporate Manager and Branch Manager order handling and by the immediate order acknowledgement channel. Messages are compact C structure images that carry no forty byte Message Header; each opens with its own two byte Transaction Code and has a length fixed by that code. Field alignment differs from the interactive encoding as well, the structures being two byte packed rather than byte packed.

### Overview

The trimmed structures replace the forty byte Message Header with a compact per message header. Transaction Code sits at offset zero of every message and is followed directly by the message body, so there is no Message Length to frame the stream; each transaction code has a fixed packet length instead.

Structures are declared with pragma pack(2) rather than pack(1), so a one byte field followed by a wider one is padded to an even offset. Those padding bytes are transcribed explicitly because the specification lists only the fields, leaving the gaps visible as jumps in the offset column. Additional Order Flags is the documented exception and stays byte packed.

The specification requires this channel to use the new Gcm encryption with the additional authentication tag described in the encryption chapter, so a capture of it is ciphertext beyond the first message unless the session keys are known.

The master list of transaction codes prints this family with its codes truncated to four digits, for example Board Lot In Tr as 2000 rather than 20000. The per structure tables carry the full five digit codes and are followed here.

### Transport

Trimmed order entry requests and responses, on the interactive connection for Corporate Manager and Branch Manager handling and on a separate port of the gateway router server for the immediate acknowledgement channel.

