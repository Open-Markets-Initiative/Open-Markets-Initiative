## Spectra Order Entry: TWIME Spectra Order Entry

Binary order entry of the Moex derivatives market through the TwimeGate gateway: new orders, iceberg orders, cancels, replaces and mass cancels, a request to the National Clearing Center for a Brokerage Firm's collateral sufficiency, and the responses, execution reports, empty book notices and trading system events the gateway returns. The gateway does not transmit market data.

### Overview

Only application messages from TwimeGate are numbered. EstablishmentAck gives the number of the next one in NextSeqNo, session messages do not advance the counter, and the client keeps its own count to find gaps. A RetransmitRequest on the trading connection recovers up to 10 messages, answered after a second; the recovery service recovers up to 1000 per request.

The flood control module limits each login to a contracted number of trading messages per second, 30 to 3000. A message over the limit is refused with FloodReject, and a client exceeding twice the limit is disconnected with Terminate code 4 (TooFastClient). A client that cannot drain its socket is disconnected with Terminate code 5 (TooSlowClient).

Between 01:00 and 05:00 Moscow time clients are disconnected, the previous session's messages are cleared and the message counter resets, so the NextSeqNo after reconnecting may be lower than before.

### Transport

Tcp connection to TwimeGate, bound to a session by Establish within ten seconds of connecting, at most one Establish per second from an address. Both sides send Sequence as a heartbeat at the KeepaliveInterval each states; a client silent for that interval is disconnected. A separate recovery service on its own address and port replays a session's messages on request.

### Key Characteristics

- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **FIXP session** - Establish, Terminate and Sequence heartbeats bind and monitor the session
- **Flood control** - Trading messages per second are limited per login and refused with FloodReject
- **Cancel on disconnect** - A silent or lost session can cancel the login's orders
- **Iceberg orders** - Iceberg orders carry a display quantity and a display variance

