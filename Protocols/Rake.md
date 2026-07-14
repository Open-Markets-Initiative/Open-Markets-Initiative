## Rake: Txse Session and Framing Layer

Payload-agnostic session and framing layer used by every Texas Stock Exchange binary protocol. RAKE defines message length prefixes, per-stream sequence numbers, packet-level session identifiers, heartbeats, and start-of-session and end-of-session semantics. It is available in a reliable session-oriented TCP variant used by SEED order entry and by market-data gap recovery, and in a multicast UDP variant used by BALE top-of-book and FEED full-depth market data.

### Overview

RAKE is the common transport foundation for the entire TXSE binary protocol suite. It provides a uniform message-framing model — length prefix, message type, optional streamId, payload — regardless of whether the payload is SEED order entry (RakeTcp), BALE top-of-book market data (RakeUdp), or FEED full-depth market data (RakeUdp). Higher-level protocols see a clean payload boundary and can extend their message bodies without breaking RAKE framing.

The TCP variant provides connection lifecycle management (logon, heartbeats, end-of-session), per-stream sequencing, and reliable in-order delivery. The UDP variant provides packet-level sequencing and lifecycle signaling (start-of-session, heartbeat, end-of-session) for real-time multicast delivery. Members recover missed UDP data by logging on to the RAKE TCP session layer and requesting replay from a specific sequence number.

### Transport

Reliable, in-order TCP delivery with connection-oriented session management. Each RAKE TCP message begins with a 2-byte length and 1-byte messageType, followed for sequenced messages by a 1-byte streamId and the higher-level protocol payload. LogonRequest / LogonResponse establish the session; MemberHeartbeat / ServerHeartbeat maintain liveness; EndOfSession terminates cleanly. TcpSequencedMessage carries Exchange-to-Member payload with per-stream sequencing; TcpUnsequencedMessage carries Member-to-Exchange payload. Used by SEED order entry, and by Member subscribers for gap recovery of RAKE UDP market data. Multicast UDP delivery for real-time market data. Each RAKE UDP packet begins with a 19-byte UdpHeader (session, sequence, messageCount, packetType) followed by messageCount length-prefixed UdpSequencedMessage frames. Each sequenced message carries a 2-byte length, 1-byte streamId, 1-byte messageType, and the higher-level protocol payload. RakeUdpPacketType signals sequenced-data / heartbeat / start-of-session / end-of-session / gap-fill variants. Used by BALE and FEED market data protocols; delivery is Exchange-to-Member only, and gap recovery is performed via the RAKE TCP session layer.

### Key Characteristics

- **Dual transport** - TCP variant for order entry and gap recovery, UDP multicast variant for real-time market data
- **Payload agnostic** - Uniform framing model reused by SEED, BALE, and FEED — no protocol-specific coupling in RAKE
- **Length-prefixed messages** - Each frame declares its own byte length so higher-level protocols can extend without breaking framing
- **Session lifecycle** - Explicit LogonRequest / LogonResponse / EndOfSession on TCP, StartOfSession / EndOfSession packet types on UDP
- **Per-stream sequencing** - Each sequenced message carries a streamId identifying the Exchange partition that produced it
- **Gap detection and recovery** - UDP subscribers detect gaps from packet sequence numbers and recover via the TCP session layer

