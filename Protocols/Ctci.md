## Ctci: Nasdaq CTCI line-oriented text messages in a binary TCP/IP envelope

Message format of the Nasdaq Computer to Computer Interface (CTCI). Each message travels in a TCP/IP envelope (a two byte length, a version, a time stamp, a logical channel, a three character message type and a sentinel) and carries line-oriented text: CR/LF delimited lines of space separated keywords and optional bracketed fields, ending with a message sequence number printed in one of several formats.

### Overview

CTCI connects a subscriber's computer to the Nasdaq Message Switch, which routes application messages (order entry, ACES and risk management) to Nasdaq application systems. SUPER messages manage the station itself (start and end of day, sequence checking, retransmission) and ADMIN messages are logged communication checks.

### Transport

TCP/IP sessions to the Nasdaq Message Switch, with logon, heartbeat, flow control and logical channel control messages in the envelope; the same message text could also be exchanged through IBM WebSphere MQ.

### Key Characteristics

- **Line-oriented text** - CR/LF delimited lines of keywords rather than fixed positions
- **Binary envelope** - Length prefixed TCP/IP envelope with logical channels
- **Message switch** - One station connection reaches several Nasdaq application systems

