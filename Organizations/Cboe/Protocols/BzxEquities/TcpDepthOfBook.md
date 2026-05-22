## BzxEquities Tcp Depth Of Book: Cboe BZX Tcp Full Depth Of Book Data (Ascii Pitch over Soup 2.0)

Tcp-based full depth of book Pitch feed publishing order events for equities traded on Cboe US Equities BZX Exchange. Messages are delivered as fixed-length non-control Ascii records framed by Soup 2.0; this is a different wire encoding from the binary Udp multicast Multicast Depth Of Book feed.

### Overview

Tcp Depth Of Book is the Tcp variant of the Cboe BZX Depth Of Book feed, providing equivalent order book events over a reliable Tcp connection instead of Ip multicast. It is designed for subscribers that cannot receive multicast feeds directly but still need full depth of book market data.

This wire format is Ascii Pitch (single-character message-type codes such as A, d, 1, E, X, P, r, 2, B, H, I, J, R, s) carrying decimal-encoded Numeric, Base 36 Numeric, Price, Long Price and Printable Ascii fields — distinct from the binary Pitch carried on the Udp multicast Multicast Depth Of Book feed. Decoders cannot be shared between the two transports.

### Transport

Tcp delivery via Soup 2.0 framing — reliable sequenced delivery as an alternative to Udp multicast. Each message is a fixed-length record made of non-control Ascii bytes; the Soup envelope handles sequencing, login, heartbeat and replay.

### Key Characteristics

- **Full depth of book** - Same set of order events as the multicast Multicast Depth Of Book feed but in Ascii encoding
- **Ascii Pitch** - Fixed-length non-control Ascii records with single-character message types
- **Soup 2.0** - Soup envelope provides login, heartbeat, sequencing and replay
- **No multicast required** - Suitable for network environments without multicast support
- **Session based** - Persistent Tcp session per subscriber

