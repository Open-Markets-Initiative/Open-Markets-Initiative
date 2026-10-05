## SesM: Session Management

MIAX's proprietary binary TCP session management protocol, used to carry recoverable application messages over a persistent connection. It provides authentication, sequencing, heartbeats and gap fill, and underlies the retransmission and order entry interfaces that complement the MACH multicast feeds.

### Overview

SesM encapsulates each higher-level application message in a packet prefixed by a length and a one-character packet type. A session opens with a Login Request naming the username, computer id, application protocol and the sequence number the client wants to resume from, and the server answers with a Login Response carrying a status and the highest sequence number it holds. When the server has replayed everything the client missed it sends a Synchronization Complete packet.

Two data packet types carry application content. Sequenced Data Packets include a sequence number and are stored by the server for replay; Unsequenced Data Packets carry no sequence number, are delivered at most once, and are the only form a client may use to send data to the server. The shape of the application message inside either packet is defined by the higher-level protocol, not by SesM.

Gap recovery has two forms. A client reconnecting may name its expected sequence number in the Login Request and have the server replay from there, or it may send a Retransmission Request naming an explicit start and end sequence number. Retransmission interfaces require the latter. Only sequenced messages can be retransmitted, and the server disconnects once the requested range has been sent.

Either side may end the session. A client sends a Logout Request and the server sends a GoodBye Packet, both carrying a reason character and free-form text; the server sends an End of Session packet when the session itself is finished and cannot be rejoined. Separate server and client Heartbeat packets are sent after one idle second, and three missed intervals indicate a lost link.

### Transport

SesM operates over a client-initiated TCP connection. Every packet opens with a two-byte length covering the packet type and payload, so a reader reassembles packets from the stream rather than relying on message boundaries. Sequenced packets carry an explicit sequence number and are recoverable; unsequenced packets are best-effort and are not counted in the sequence space.

### Key Characteristics

- **Length prefixed** - Two-byte length covering packet type and payload allows packet reassembly from the Tcp stream
- **Authenticated login** - Username, computer id and application protocol are validated before any message is accepted
- **Sequenced and unsequenced** - Recoverable sequenced packets alongside best-effort unsequenced packets in a separate space
- **Gap fill** - Replay from a requested sequence number at login, or an explicit retransmission request range
- **Heartbeat monitoring** - Independent server and client heartbeats after one idle second for link failure detection
- **Explicit termination** - Logout, GoodBye and End of Session packets each carry a reason for the disconnect
- **Protocol agnostic** - The application message inside a data packet is defined entirely by the higher-level protocol

