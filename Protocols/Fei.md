## Fei: Futures Express Interface

MIAX's binary order entry message set for the MIAX Futures Onyx trading platform, with which MIAX Futures Exchange members and sponsored firms submit, modify and cancel futures orders, create strategies and receive order and execution notifications. Messages combine binary numeric fields, fixed length ASCII fields and bit fields, and each is carried in a SesM packet.

### Overview

FEI is a gateway interface that gives a client order entry to a single MIAX Futures Onyx Matching Engine, each Matching Engine handling trading for its own set of instruments. Order acknowledgements and cancel acknowledgements come directly from the Matching Engine. Messages refer to instruments by Instrument IDs rather than full canonical symbols, and the Instrument IDs tradable on each Matching Engine are published on the DOM, TOM and FXD feeds.

Each message opens with a two character message type. Liquidity messages are the New Order, Modify Order, Cancel Order, Mass Cancel and Strategy Creation requests and their responses; notifications report system state, new and modified orders, reserve replenishment, cancels and size reductions, order status updates, and simple and complex executions.

Numeric fields are Intel x86 byte ordered (little-endian) binary, unsigned or signed. Prices carry nine implied decimal places, times are nanoseconds or milliseconds since the UNIX epoch, the Business Trade Date is a count of days since the UNIX epoch, alphanumeric fields are left justified and padded with spaces, and string fields are null terminated when shorter than the field. On receipt of an unknown, malformed or illegal message FEI sends a SesM Goodbye Packet with a reason and disconnects.

### Transport

FEI requires TCP/IP for guaranteed delivery of order packets, and firms connect with SesM-TCP, the MIAX session management protocol that provides authentication, sequencing, heartbeats and gap fill. All notifications are sequenced messages; messages of no value after a reconnect are sent unsequenced.

### Key Characteristics

- **Binary orders** - Binary numeric fields, fixed length ASCII fields and bit fields for low latency
- **Little endian** - Unsigned and signed numbers in Intel x86 byte order
- **Implied decimals** - Prices carry nine implied decimal places
- **Single Matching Engine** - Each gateway session reaches one Matching Engine and its instruments
- **SesM session** - Carried over SesM-TCP for authentication, sequencing and gap fill

