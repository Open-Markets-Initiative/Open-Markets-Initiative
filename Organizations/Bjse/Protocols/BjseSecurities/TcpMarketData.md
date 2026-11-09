## BjseSecurities Tcp Market Data: Bjse Tcp Market Data

Real time and retransmitted market data of the Beijing Stock Exchange, delivered over a session to the market quotation gateway (BJQG). The session carries the same message set as the multicast feed, preceded by Logon, Logout and Heartbeat session management, and adds the retransmission request that recovers missed tick data and announcement files.

### Overview

Only tick data and announcement files can be retransmitted. A subscriber detects a tick gap from the channel code and message sequence number, then asks for the missing range with a Retransmission Message naming the channel and a sequence range; an ending sequence number of zero means everything the gateway still holds in memory for that channel. The gateway answers requests in arrival order and closes each one with a Retransmission Message carrying a status.

Announcement files are recovered in two steps. A subscriber first requests the announcement summary, a text list of every announcement issued, then requests the missing files one at a time by identifier. The specification recommends requesting the announcement files immediately after logon.

The gateway applies flow control by disconnecting. If a subscriber cannot keep up and the messages queued for it exceed the gateway threshold, the gateway drops the connection immediately and the subscriber should attempt to reconnect.

### Transport

Standard point to point Tcp connection to the market quotation gateway, which offers a real time data port and a retransmission port, each accepting one connection; only the network version gateway offers the retransmission port. A Logon establishes the session and the gateway confirms it with a Logon of its own, or refuses it with a Logout carrying a session status. Each message carries the modulo 256 sum of its header and body in a trailing checksum.

### Key Characteristics

- **Session managed** - Logon, Logout and Heartbeat with a documented session status on refusal
- **Two ports** - A real time data port and a retransmission port, one connection each
- **Tick retransmission** - Missed tick data recovered by channel and sequence range, answered in arrival order
- **Announcement recovery** - A summary list of every announcement, then the missing files one at a time
- **Per message checksum** - Each message carries the modulo 256 sum of its header and body
- **Disconnect on backlog** - Flow control is a disconnection once the queue exceeds the gateway threshold

