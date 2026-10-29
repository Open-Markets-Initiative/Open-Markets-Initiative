## ESesM: Extended Session Management

MIAX's proprietary binary TCP session management protocol for MIAX Pearl Equities. It extends SesM so that a single connection reaches every Matching Engine, each delivering its own sequenced stream, and it provides authentication, sequencing, heartbeats and gap fill beneath interfaces such as MIAX Express Orders and Top of Market Retransmission.

### Overview

ESesM extends MIAX SesM. Where SesM serves one Matching Engine per connection, ESesM lets a client interact with all Matching Engines on the same connection: messages from each Matching Engine arrive as a separate sequenced stream that identifies the engine it came from, and the client stays connected to the others when one Matching Engine is unavailable.

Each Matching Engine's stream belongs to a trading session identified by a Trading Session ID, which starts at 1 and normally lasts the trading day. When a Matching Engine recovers it starts a new trading session with the next Trading Session ID and sequence numbers starting again at 1, and the server announces it with a Trading Session Update packet; messages from the earlier session can no longer be replayed.

A session opens with a Login Request naming the ESesM version, username, computer id and application protocol, followed by the number of Matching Engines and, for each, the requested trading session and the sequence number the client wants to resume from. The server answers with a Login Response carrying, for each Matching Engine, a status, the current Trading Session ID and the highest sequence number it holds, and sends a Synchronization Complete packet per Matching Engine once it has replayed what the client missed.

Sequenced Data Packets carry an eight-byte sequence number and the one-byte ID of the Matching Engine that originated the message, and are retained by the server for replay. Unsequenced Data Packets carry neither, are delivered at most once, and are the only form a client may use to send data to the server. Gap fill is either a replay from the sequence numbers named at login or a Retransmission Request naming a start and end sequence number to a retransmission server for one Matching Engine, which disconnects once it has sent the range.

Numbers are unsigned little-endian binary and text fields are alphanumeric, left justified and padded with spaces. Server and client Heartbeat packets are sent after more than one second without data, and three missed intervals indicate a lost link. The client ends a session with a Logout Request and the server with a GoodBye Packet, both carrying a reason and free-form text, and either side may send a Test packet of human readable text that the other ignores.

### Transport

ESesM is built on top of a client-initiated TCP/IP connection. Every packet opens with a two-byte length covering the rest of the packet, followed by a one-character packet type, so a reader reassembles packets from the stream rather than relying on network packet boundaries. A packet's payload is exactly one application message of at most 65,534 bytes.

### Key Characteristics

- **Length prefixed** - Two-byte length covering the rest of the packet allows packet reassembly from the Tcp stream
- **All Matching Engines** - One connection carries a separate sequenced stream from every Matching Engine
- **Authenticated login** - ESesM version, username, computer id and application protocol are validated at login
- **Trading sessions** - Each Matching Engine stream is scoped by a Trading Session ID that restarts its sequence on recovery
- **Gap fill** - Replay per Matching Engine from login, or an explicit retransmission request range
- **Heartbeat monitoring** - Independent server and client heartbeats after one idle second for link failure detection
- **Protocol agnostic** - The application message inside a data packet is defined entirely by the higher-level protocol

