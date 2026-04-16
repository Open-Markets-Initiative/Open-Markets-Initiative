## Xmt: Tmx Toronto Stock Exchange Xmt Feed

Market data feed variant for the Tmx Toronto Stock Exchange publishing real-time quote and trade events over the Xmt message format.

### Overview

Xmt is a Tmx market data product for the Toronto Stock Exchange family of venues, publishing quote updates, trade reports, and session events using the Xmt binary message format. It is available as an alternative to the Broadcast Feed for subscribers that integrate against the Xmt wire format.

### Transport

Udp multicast via the Sola transport framing for real-time delivery of sequenced messages with per-packet sequence numbers for gap detection. Tcp for the Sola gap fill and retransmission services used by subscribers to recover missed multicast messages.

### Key Characteristics

- **Tmx Xmt format** - Alternative binary message format for Tmx market data
- **Tsx coverage** - Toronto Stock Exchange listed securities
- **Multicast delivery** - Real-time Udp multicast distribution
- **Gap recovery** - Tcp gap fill and retransmission service
- **Quote and trade events** - Full market data coverage

