## Oasis Control Channel: Iocp Control Channel

Control channel of the Internet Oriented Communication Portal, through which a data vendor authenticates and controls the transmission and retransmission of the Ids market data feed of every venue on the Oasis platform, including the Hellenic Energy Exchange markets.

### Overview

The client sends five requests, Login, Close Connection, Channel Status, Transmission and Retransmission, and the Iocp answers each with a reply carrying a result code. The Iocp also sends an Authentication Challenge when the control channel opens, and General Error and General Notification messages when a systemic or transaction event occurs.

A client may run up to three retransmissions at once. A General Notification tells it when one has ended.

### Transport

Tcp control connection opened before the data connection; the Iocp challenges, the vendor logs in, and every later request and reply travels on this channel.

### Key Characteristics

- **Request and reply** - Five client requests, each answered by a server reply with a result code
- **Retransmission by range** - Retransmissions requested by serial number range and stopped by their ID

