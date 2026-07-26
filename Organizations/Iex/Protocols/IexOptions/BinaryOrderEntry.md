## IexOptions Binary Order Entry: Iex Options Binary Order Entry

Sbe-encoded binary order entry protocol for Iex Options carrying order submission, cancel replace, mass cancel, purge, and execution reporting over a framed Tcp session with subsession support.

### Overview

The Iex Options binary order entry protocol is built from two Sbe schemas sharing one Tcp session: a session schema handling login, heartbeats, logout, terminate, sequenced message delivery, and subsession management, and a business schema carrying new order single, cancel replace, cancel, mass cancel, purge, and the corresponding acknowledgement and execution report messages.

Each framed packet is a two-byte little-endian length followed by an Sbe message header whose schema id distinguishes session messages from business messages. Subsessions let a firm multiplex independently sequenced order flows over one physical connection.

### Transport

Tcp carrying length-framed Sbe packets — session schema messages for login, heartbeat, subsession join and leave, and terminate, plus business schema messages for the order lifecycle.

### Key Characteristics

- **Options order entry** - Order submission, replace, cancel, and execution reports
- **Sbe encoded** - Simple Binary Encoding session and business schemas
- **Length-framed Tcp** - Two-byte length prefix then Sbe header on every packet
- **Two schemas** - Session (20000) and business (20001) schemas share the session
- **Subsessions** - Independently sequenced order flows multiplexed on one connection
- **Mass cancel and purge** - Bulk risk controls alongside single-order operations

