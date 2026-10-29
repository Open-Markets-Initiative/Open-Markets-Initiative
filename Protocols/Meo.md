## Meo: Miax Express Orders

MIAX's binary order entry message set for MIAX Pearl Equities, with which members and sponsored firms submit, modify and cancel equity orders and receive order and execution notifications. Messages combine binary numeric fields, fixed length ASCII fields and bit fields, and each is carried in an ESesM packet.

### Overview

MEO is a gateway interface that gives a client order entry to all MIAX Pearl Equities Matching Engines, routing each order to the appropriate Matching Engine by its security symbol. Order acknowledgements and cancel acknowledgements come directly from the Matching Engine. Messages refer to securities by Symbol IDs rather than full canonical symbols, and the Symbol Update administrative message disseminates the Symbol IDs assigned for the current trading session.

Each message opens with a two character message type. Liquidity messages are the New Order, Modify Order, Cancel Order, Cancel Order by Exchange Order ID and Mass Cancel requests and their responses; notifications report system state, new and modified orders, cancels and size reductions, price updates, reserve replenishment and executions.

Numeric fields are Intel x86 byte ordered (little-endian) binary, unsigned or signed. Prices carry six implied decimal places, times are nanoseconds since the UNIX epoch, alphanumeric fields are left justified and padded with spaces, and string fields are null terminated when shorter than the field. On receipt of an unknown, malformed or illegal message MEO sends an ESesM Goodbye Packet with a reason and disconnects.

### Transport

MEO requires TCP/IP for guaranteed delivery of order packets, and firms connect with ESesM-TCP, the MIAX session management protocol that provides authentication, sequencing, heartbeats and gap fill. Notifications are sequenced messages that carry the number of the Matching Engine that originated them; messages of no value after a reconnect are sent unsequenced.

### Key Characteristics

- **Binary orders** - Binary numeric fields, fixed length ASCII fields and bit fields for low latency
- **Little endian** - Unsigned and signed numbers in Intel x86 byte order
- **Implied decimals** - Prices carry six implied decimal places
- **All Matching Engines** - One gateway routes orders to the Matching Engine for each symbol
- **ESesM session** - Carried over ESesM-TCP for authentication, sequencing and gap fill

