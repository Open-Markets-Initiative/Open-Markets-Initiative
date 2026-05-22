## AsciiPitch: Cboe ASCII variant of Pitch (line-oriented, TCP)

Line-oriented ASCII variant of the Cboe Pitch market data protocol. Carries the same per-order add/modify/cancel/execute semantics as binary Pitch but encodes each message as a fixed-length printable record terminated by a newline, delivered over TCP — either as a plain TCP byte stream (Top of Book, low-rate feeds) or framed by Cboe Soup 2.0 for sequencing and recovery (TCP Depth of Book, Auction Feed, Last Sale).

### Overview

ASCII Pitch is the line-oriented text variant of the Cboe Pitch family. Where binary Pitch packs each event into a fixed-length little-endian binary record delivered over UDP multicast, ASCII Pitch encodes the same event types (add order, cancel, execute, trade, status, …) as printable ASCII fields terminated by a newline, and delivers them over TCP. The trade-off is reduced bandwidth efficiency in exchange for human-readable wire bytes and connection-oriented reliable delivery.

The encoding underpins Cboe's TCP-delivered market data products including Top of Book, TCP Depth of Book, Auction Feed, and Last Sale across the BYX, BZX, EDGA, EDGX equity exchanges and the Titanium consolidated equities and options books. Two TCP framing variants are observed in the wild: plain unsequenced TCP (Top of Book and similar low-rate feeds) and Cboe Soup 2.0 framing (higher-rate feeds where sequencing and replay are required).

Message types and field layouts mirror binary Pitch closely — each ASCII record begins with a single-character message type code identifying the event, followed by fixed-width ASCII fields for timestamps (nanoseconds since midnight), prices (decimal with implied precision), quantities, order IDs, and so on. Subscribers parse one record per newline and apply the same order-book reconstruction logic used for binary Pitch.

### Transport

Direct TCP unicast — each subscriber connects to a Cboe-assigned host/port and receives line-oriented ASCII Pitch messages delimited by newline. Typical of Top of Book feeds; recovery is performed by reconnecting and requesting a spin of the current state. Cboe Soup 2.0 framing (Cboe/Common/Headers/Soup.v2.0.Source.xml) wraps each ASCII Pitch message in a sequenced envelope, providing gap detection and replay over a single TCP session. Used by TCP Depth of Book, Auction Feed, and Last Sale variants where reliable in-order delivery matters more than the lowest possible latency.

### Key Characteristics

- **Line-oriented ASCII** - Fixed-length printable records terminated by newline; each record is one event
- **TCP delivery** - Delivered over TCP unicast — plain byte stream or Cboe Soup 2.0-framed depending on the feed
- **Pitch event semantics** - Carries the same add/modify/cancel/execute/trade/status events as binary Pitch
- **Spin recovery** - On the unsequenced TCP variant, reconnect-and-spin replays the current state
- **Soup 2.0 recovery** - On the framed variant, Cboe Soup 2.0 supplies sequence numbers and replay over a single session
- **Multi-platform coverage** - Used across BYX, BZX, EDGA, EDGX, and Titanium consolidated equities and options books

