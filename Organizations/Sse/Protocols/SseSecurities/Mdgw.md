## SseSecurities Mdgw: Market Data Gateway

The BINARY interface specifies the transmission of market data between the Shanghai Stock Exchange Market Data Gateway (MDGW) and user market data systems.

### Overview

The first message the user system sends must be a Logon. On success the gateway answers with a Logon; on failure it sends a Logout with the reason, and the user system closes the connection. The user system may send other messages only after it receives the gateway Logon.

Each message of a session carries a message sequence number, which normally starts at 1 and increases continuously until the session ends. Repeated logons by one user system in a trading day are separate sessions.

Market data snapshot messages cannot be re-transmitted. Tick by tick market data messages can be re-transmitted.

Both sides send Heartbeat messages during idle periods, at a minimum interval set by HeartBtInt in the Logon. If the user system receives no message from the gateway for more than two HeartBtInt periods, it must re-establish the session.

The gateway closes the session itself when, among other cases, the user system does not log on within the set time, does not close the connection after a failed logon or a logout, or does not process data fast enough and the queued messages exceed a threshold.

### Transport

User market data systems receive streaming market data from MDGW over TCP. MDGW is the server, and the user system initiates the connection. Data is not encrypted; the access user network provides transmission security.

### Key Characteristics

- **Session managed** - Logon, Logout and Heartbeat manage the session, and a Logout carries the reason for a failed logon
- **Tick re-transmission** - Tick by tick market data can be re-transmitted, snapshots cannot
- **Per message checksum** - Each message ends with a checksum of its header and body
- **Disconnect on backlog** - The gateway closes the session when the messages queued for the user system exceed a threshold

