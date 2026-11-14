## Ctd: Miax Clearing Trade Drop

MIAX's binary messaging interface that provides real-time clearing trade information to the parties of a trade, and to entitled designated recipients, on the MIAX options exchanges. Messages combine binary numeric fields and fixed length ASCII fields, and each is carried in a SesM packet.

### Overview

The exchange's trading architecture consists of multiple trading engines, each handling all options for a set of underlyings. The CTD acts as a gateway, collecting the trades from each trading engine and providing a consolidated flow of trades to the recipients of the CTD output. Messages support entitlements by OCC Number, CMTA and clearing member MPID.

Each message opens with a one character message type. The System State message notifies firms of system state changes such as the end of application messages and the start and end of test sessions; the Trade message carries trades, trade corrections and trade cancels, with clearing details for this side and the contra side of the trade; the Risk Notification message reports Risk Protection Monitor events.

Numeric fields are unsigned, Intel x86 byte ordered (little-endian) binary. Prices carry four implied decimal places, times are nanoseconds since midnight, and time fields in all messages are in United States Eastern time. Alphanumeric fields are left justified and space padded. Trade conditions are intended to be aligned with the OPRA trade conditions as a convenience.

System State and Trade messages are sequenced and recoverable. Risk Notification messages are sequenced or unsequenced by event type: solicited event types are sequenced messages at the SesM protocol level and recoverable, while the unsolicited period status notification is unsequenced and not recoverable. Retransmitted trades are recognised by Trade ID, Correction Number, Side and Trade Action together.

### Transport

CTD requires the TCP/IP based MIAX proprietary SesM protocol to provide guaranteed delivery of CTD sourced messages, with authentication, sequencing of messages, heartbeats and gap fills. Recipients maintain a primary and a secondary port connection; when connecting to the backup, firms log in to receive messages from sequence number 1, since SesM sequence numbers and message ordering may differ on the backup session.

### Key Characteristics

- **Clearing trades** - Real-time clearing trade information to the parties of a trade
- **Entitlements** - Delivery by OCC Number, CMTA and clearing member MPID
- **Little endian** - Unsigned binary numbers in Intel x86 byte order
- **Implied decimals** - Prices carry four implied decimal places
- **Eastern time** - Nanoseconds since midnight, US Eastern time
- **SesM session** - Carried over SesM TCP for authentication, sequencing and gap fill

