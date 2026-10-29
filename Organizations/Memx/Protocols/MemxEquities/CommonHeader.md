## MemxEquities Common Header: MEMX-UDP and MEMX-TCP session layer headers

Common headers of MEMX-UDP, a UDP broadcast-only session layer for delivery of business messages without guaranteed delivery, and MEMX-TCP, a TCP session layer for reliable delivery of business messages, used to fill gaps from MEMX-UDP or for streaming data.

### Overview

The MEMX-UDP v1.1 common header is 18 bytes: a 1-byte Message Type, a 1-byte Header Length, an 8-byte Session ID and an 8-byte Sequence Number. Message Type 0 is a Heartbeat and 1 a Session Shutdown, both carrying the highest published sequence number and nothing after the header; 2 is a Sequenced Message, whose header is followed by a 2-byte Message Count and that many messages, each a 2-byte Message Length and the message payload. The first message has the header's Sequence Number and each following message increments it by one.

The MEMX-TCP v1.2 common header is a 1-byte Message Type and a 2-byte Message Length counting the bytes after the header. After a Login Request and Login Accepted the client receives a Start of Session with the current Session ID and may send a Replay, ReplayAll or Stream request, which the server begins with Replay Begin or Stream Begin and answers with Sequenced Messages. Clients may send Unsequenced Messages during a Stream session, and heartbeats are sent both ways. A malformed or unexpected session-level message disconnects the client.

All fields of both protocols are big endian, and numeric fields are unsigned. MEMO SBE order entry is carried by MEMX-TCP in stream mode, and MEMOIR market data by MEMX-UDP with MEMX-TCP as the gap fill replay service.

### Transport

MEMX-UDP datagrams from a single broadcast source, with no messages from the consumer back to the source; missed data is recovered out of band, such as by MEMX-TCP. MEMX-TCP connections, logged in with a token, served in Replay, Stream or Snapshot request mode as stated in the Login Accepted message.

### Key Characteristics

- **Udp sequenced datagrams** - Message type, header length, session ID and sequence number on every datagram
- **Message count and length** - Sequenced Message datagrams carry a count of 2-byte length-prefixed messages
- **Heartbeat and shutdown** - Udp heartbeats and session shutdowns carry the highest published sequence number
- **Tcp request modes** - Replay, Stream or Snapshot mode stated by the server at login
- **Tcp framing** - 1-byte message type and 2-byte message length on every message
- **Big endian** - All fields in network byte order, numeric fields unsigned

