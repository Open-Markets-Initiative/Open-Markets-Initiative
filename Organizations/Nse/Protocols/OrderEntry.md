## Order Entry: Order Entry

Nse's order entry interface for member built front ends, published as the Trimmed Protocol for Non-Neat Front End. Members log on to a gateway server, download the local database of contracts and participants, then enter, modify and cancel orders and receive their confirmations over the bidirectional Interactive Virtual Circuit. The one way Broadcast Circuit that carries market data to the same front end is a separate encoding and a separate specification.

### Overview

Every message is prefaced by a forty byte header. The interactive circuit uses Message Header, whose Transaction Code at offset zero selects the message and whose Message Length at offset thirty eight gives the length of the whole message including the header. Responses embedded in a download reply use Inner Message Header, which carries the same fields in a different order, and the broadcast circuit uses Bcast Header.

The two circuits are not a strict partition of the transaction code space. Several codes named Bcast travel on the interactive circuit as part of the local database download, and Spread Market by Price is documented as arriving on the broadcast circuit or, when broadcast is unavailable, on the interactive one. A transaction code alone therefore does not identify the circuit.

### Transport

Interactive Virtual Circuit, bidirectional between the front end and the host, carrying every request, its response, and unsolicited messages such as trade confirmations.

### Key Characteristics

- **Header addressed** - A forty byte header prefaces every message and its Transaction Code selects the structure
- **Big endian** - Fixed width fields, byte packed, big endian on the wire
- **Token addressed** - Contracts are referenced by numeric Token resolved through the downloaded local database
- **Length delimited** - Message Length gives the whole message including its header, framing the Tcp byte stream

