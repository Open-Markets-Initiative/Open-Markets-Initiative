## Mei: Miax Express Interface

MIAX's binary quoting interface for the MIAX options exchanges, with which approved Market Makers submit bulk quotes, enhanced quotes and complex enhanced quotes, manage their ARM and liquidity protections, and receive series, strategy, protection, cancel and execution notifications. Messages combine binary numeric fields, fixed length ASCII fields and variable length bulk messages, and each is carried in a SesM packet.

### Overview

MEI is the interface MIAX members approved as Market Makers use to quote on the options market. A firm connects to one or more servers on each matching engine cloud, and quote and quote cancel acknowledgements come directly from the engine. Messages refer to options by Product IDs and to complex strategies by Strategy IDs rather than full canonical symbols; the Simple Series Update and Complex Strategy Definition messages disseminate the IDs assigned for the current session.

Each message opens with a two character message type. Liquidity messages are the simple bulk quote, simple and complex eQuote, mass cancel and protection reset requests and their responses; administrative messages carry the series list, ARM and ARM2 settings and valid quote widths; notifications report system state, trading status, quote width relief, ARM and liquidity protection triggers, cancels and executions.

Numeric fields are Intel x86 byte ordered (little-endian) binary, unsigned or signed. Prices carry four implied decimal places, NanoTime fields are nanoseconds since midnight and TimeStamp fields nanoseconds since the Epoch, with time fields in United States Eastern time, and alphanumeric fields are left justified and padded with spaces. On receipt of an unknown, malformed or illegal message MEI sends a SesM Goodbye Packet with a reason and disconnects.

### Transport

MEI requires TCP/IP for guaranteed delivery of quote packets, and firms connect with SesM-TCP, the MIAX session management protocol that provides authentication, sequencing of messages, heartbeats and gap fills. Messages of no value for refreshing after a reconnect are sent unsequenced.

### Key Characteristics

- **Market Maker quoting** - Bulk quotes, enhanced quotes and complex enhanced quotes for assigned underlyings
- **Little endian** - Unsigned and signed numbers in Intel x86 byte order
- **Implied decimals** - Prices carry four implied decimal places
- **Risk protection** - ARM, ARM2, single side and SLAP protections set and reset through the interface
- **SesM session** - Carried over SesM-TCP for authentication, sequencing and gap fill

