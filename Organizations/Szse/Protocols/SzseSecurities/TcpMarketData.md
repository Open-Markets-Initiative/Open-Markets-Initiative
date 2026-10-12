## SzseSecurities Tcp Market Data: Szse Tcp Market Data

Real time and re-transmitted market data of the Shenzhen Stock Exchange fifth generation trading system, delivered over a session to the Market Data Gateway. The session carries the same message set as the multicast feed, preceded by Logon, Logout and Heartbeat session management, and adds the re-transmission request that recovers missed tick data and announcement files.

### Overview

Only tick data and announcement files can be re-transmitted. A subscriber detects a tick gap from the channel code and message sequence number, then asks for the missing range with a Re-transmitting Message naming the channel and a sequence range; an ending sequence number of zero means everything the gateway still holds in memory for that channel. The gateway answers requests in arrival order and closes each one with a Re-transmitting Message carrying a status. Snapshot data, including the real time status of a security, is published at a fixed interval and cannot be re-transmitted.

Announcement files are recovered in two steps. A subscriber first requests the announcement summary, an aggregate text list of the identity, name, size and time of every announcement issued, then requests the missing files one at a time by identity. The specification recommends requesting the summary immediately after logon.

The gateway applies flow control by disconnecting. If a subscriber cannot keep up and the messages queued for it exceed the gateway threshold, the gateway drops the connection immediately and the subscriber must reconnect.

### Transport

Standard point to point Tcp connection to the Market Data Gateway. The gateway offers a real time data port, 9129 by default, and a re-transmission port, 9130 by default, and each port accepts one connection; only the Internet Version gateway offers the re-transmission port. A Logon establishes the session and the gateway confirms it with a Logon of its own, or refuses it with a Logout carrying a session status. Each message carries the modulo 256 sum of its header and body in a trailing checksum.

### Key Characteristics

- **Session managed** - Logon, Logout and Heartbeat with a documented session status on refusal
- **Two ports** - A real time data port and a re-transmission port, one connection each
- **Tick re-transmission** - Missed tick data recovered by channel and sequence range, answered in arrival order
- **Announcement recovery** - A summary list of every announcement, then the missing files one at a time
- **Per message checksum** - Each message carries the modulo 256 sum of its header and body
- **Disconnect on backlog** - Flow control is a disconnection once the queue exceeds the gateway threshold

