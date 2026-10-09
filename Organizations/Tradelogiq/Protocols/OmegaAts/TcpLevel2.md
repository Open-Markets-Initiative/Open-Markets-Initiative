## OmegaAts Tcp Level2: Omega Tcp Level 2

The Omega ATS Level 2 Itch message set delivered over a point to point SoupTCPBinary session rather than Qtp multicast. The message content is identical to the multicast feed; each Sequenced Data Packet carries exactly one Itch message and the sequence number is implied, the Login Accepted Packet naming the next sequenced message and the count advancing by one per packet, so a client that loses its socket can re-log in and resume without a gap.

### Overview

Tradelogiq offers the SoupTCP protocol as an alternative to Qtp multicast for carrying Itch 5.0. The server sends Login Accepted, Login Rejected, Sequenced Data and Server Heartbeat packets; the client sends Login Request, Unsequenced Data, Client Heartbeat and Logout Request packets. Tradelogiq v1.03 carries no End of Session packet and no Debug packet.

Sequenced Data Packets do not contain an explicit sequence number. Both client and server compute it locally by counting messages, the first sequenced message of a session always being 1, and the Login Accepted Packet naming the next one to be sent.

### Transport

SoupTCPBinary v1.03 session, a two byte packet length and one byte packet type framing each logical packet, with login, logout and bidirectional heartbeats and guaranteed in order delivery of every sequenced message across socket failures.

### Key Characteristics

- **Full order depth** - The same Level 2 Itch message set the multicast feed carries
- **SoupTcp Binary session** - Point to point Tcp with login, logout and heartbeats
- **Implied sequencing** - One message per Sequenced Data Packet, the sequence counted locally
- **Guaranteed delivery** - A client re-logs in with its next expected sequence number after a socket failure

