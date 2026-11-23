## Lse24 Native Trading Gateway: LSE 24 Native Trading Gateway

Native Trading Gateway order entry interface of LSE 24 on the Lseg Millennium Exchange platform, carrying order and quote submission, amendment and cancellation over a bidirectional Tcp session.

### Overview

LSE 24 runs the main market's Native Trading Gateway, documented as LSE 24 MIT203: the same messages, layouts and values. Its section 11 lists what LSE 24 does not offer: the Pegged, Pegged Limit and Offset order types, the OPG, ATC, GFX, GFA, GTD, GTT, GFS, CPX, AVD and AVC validity types, six of the RFQ models and electronic/executable quotes.

The Native Trading Gateway is the low latency binary order entry interface to the Millennium Exchange matching engine, documented as MIT203. Clients submit new orders, cancels, cancel/replaces and mass cancels, and receive execution reports covering acceptance, rejection, execution, expiry, cancellation and restatement.

The gateway also carries the request for quote workflow. A Requester submits an RFQ, market makers respond with quotes, and the server relays requests, quotes, acknowledgements and execution reports between the two sides. Several of these message types travel in both directions with the same wire layout, distinguished only by which side transmitted them.

Sessions are established with a Logon carrying a user name and password, maintained with heartbeats, and terminated with a Logout. Messages missed during a disconnect are recovered by logging into the recovery channel and issuing a Missed Message Request, which the server acknowledges and completes with a report.

### Transport

Bidirectional Tcp session between the client and the trading gateway, framed by a four byte message header and recovered through a separate recovery channel that replays missed messages.

### Key Characteristics

- **Native binary** - Fixed width little endian binary messages rather than Fix tags
- **Bidirectional session** - Client and server both transmit; several message types are shared by both sides
- **Order and quote handling** - Order submission and amendment alongside the request for quote workflow
- **Message recovery** - A separate recovery channel replays messages missed during a disconnect
- **Partitioned** - Instruments are distributed across matching partitions, identified per message

