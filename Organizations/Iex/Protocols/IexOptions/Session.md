## IexOptions Session: Iex Options Binary Session Layer

Sbe-encoded binary session layer for Iex Options order entry handling login, heartbeat, logout, terminate, sequenced message delivery, and subsession join and leave.

### Overview

The Iex Options binary session protocol is the Sbe session schema underpinning binary order entry. It covers login request and response, gateway and client heartbeats, logout, terminate, the sequenced message header, and subsession join and leave with their responses, providing authentication, liveness detection, and independently sequenced subsession flows over one Tcp connection.

### Transport

Tcp carrying length-framed Sbe session messages providing the authenticated delivery path for the Iex Options business schema.

### Key Characteristics

- **Sbe encoded** - Session schema consistent with the business schema encoding
- **Authentication** - Login request and response with logon id and token
- **Heartbeat monitoring** - Gateway and client heartbeats detect connection failures
- **Subsessions** - Join and leave independently sequenced flows on one connection
- **Graceful termination** - Logout and terminate teardown procedures

