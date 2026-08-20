## Millennium Trading: Fix Trading Gateway

Fix Trading Gateway order entry interface for the Lseg Millennium Exchange platform, enabling member firms to submit orders and quotes and to receive real time information on executed trades.

### Overview

The Fix Trading Gateway is the tagged Ascii order entry interface to the Millennium Exchange matching engine, documented as MIT202. It is the counterpart to the Native Trading Gateway of MIT203, offering the same trading services over industry standard Fix rather than a proprietary binary encoding.

The gateway carries order handling and quote handling, including the request for quote models, alongside security identification, party identification and market operations. Auto cancel on disconnect and mass cancellation on disconnect protect resting interest when a session drops.

A client initiates a session each trading day with a Logon identifying itself by SenderCompID, which the server validates together with the password and the source IP address. Client and server each maintain independent inbound and outbound sequence numbers, initialised to one at the start of the day, and missed messages are recovered in session through Fix Resend Requests. A Fix session does not continue into the next trading day.

### Transport

Point to point Tcp session carrying a Fix 5.0 Service Pack 2 application layer over a FIXT 1.1 session layer, with each client assigned an IP address and port.

### Key Characteristics

- **Fix 5.0 SP2** - Fix 5.0 Service Pack 2 application layer over a FIXT 1.1 session layer
- **Tagged Ascii** - Self describing tag equals value fields rather than the fixed width binary of the Native gateway
- **Order and quote handling** - Order submission and amendment alongside the request for quote workflow
- **In session recovery** - Missed messages are replayed through Fix Resend Requests rather than a separate recovery channel
- **Daily sequence numbers** - Sequence numbers are initialised to one at the start of each trading day and a session does not span days

