## TcpOut: TcpOut

Simple length delimited encapsulation layer used by CIX Trading Inc. for outbound Tcp data dissemination. Each packet is a 2-byte little endian Length inclusive of itself, a 1-byte Ascii Packet Type, and a type specific body. Session packets carry Login, Successful Login, Login Reject and heartbeats in both directions, while the Binary Data packet wraps one application message as a bare Message Type byte plus payload.

### Overview

TcpOut is the transport CIX uses to hand outbound data to a connected client, currently the Tcp Snapshot recovery service. It adds only framing and session management, leaving message semantics to the encapsulated application protocol.

Unlike the Aspen multicast message header, whose Length excludes the Length field itself, the TcpOut Length is inclusive: a heartbeat is 3 bytes and reports Length 3. Encapsulated application messages carry no inner length prefix, so a Binary Data packet body is a Message Type byte followed by Length minus 4 bytes of payload.

### Transport

Tcp stream of length delimited packets, reassembled on the inclusive Length field. TcpOut is a separate protocol from the CIX multicast and rerequest feeds and carries no Udp header.

### Key Characteristics

- **Length delimited** - 2-byte little endian Length inclusive of itself frames every packet
- **Ascii packet types** - Single Ascii byte selects session or data packet
- **Session management** - Login, Successful Login, Login Reject and heartbeats in both directions
- **Application encapsulation** - Binary Data packet wraps one application message with no inner length prefix

