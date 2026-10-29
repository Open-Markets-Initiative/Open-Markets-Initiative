## PearlEquities ESes M: Miax Pearl Equities Extended TCP Session Management

MIAX Pearl Equities session management protocol over Tcp, extending SesM so that one connection reaches every Matching Engine, with authentication, per Matching Engine sequencing, heartbeats and gap fill beneath interfaces such as MIAX Express Orders and Top of Market Retransmission.

### Overview

ESesM is the MIAX Pearl Equities Extended TCP Session Management protocol, a lightweight point-to-point protocol built on top of TCP/IP. It extends MIAX SesM: where SesM serves one Matching Engine per connection, ESesM lets a client interact with all Matching Engines on the same connection, each delivering its own sequenced stream that identifies the engine it came from, and keeps the client connected to the others when one Matching Engine is unavailable.

ESesM is opaque to the higher-level protocols it carries. Each data packet holds exactly one application message, sequenced packets for messages the client must be able to recover and unsequenced packets delivered at most once. Gateway interfaces such as MIAX Express Orders recover gaps by naming each Matching Engine's next expected sequence number at login, while retransmission interfaces such as Top of Market Retransmission use a Retransmission Request for an explicit range and then disconnect.

### Transport

Tcp connection opened by the client and authenticated by a Login Request, carrying length prefixed sequenced and unsequenced data packets alongside login, synchronization, retransmission, trading session update, heartbeat, logout, goodbye and test packets.

### Key Characteristics

- **All Matching Engines** - One connection carries a sequenced stream from every Matching Engine
- **Authentication** - Login request validated by ESesM version, username and computer id
- **Trading sessions** - Each Matching Engine stream is scoped by a Trading Session ID
- **Gap fill** - Replay from login or an explicit retransmission request range
- **Heartbeat** - Server and client heartbeats after one idle second
- **Tcp delivered** - Session state carried over a persistent Tcp connection

