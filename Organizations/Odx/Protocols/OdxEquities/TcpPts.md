## OdxEquities Tcp Pts: Odx Equities Itch Market Data over SoupBinTcp

The Odx equities Itch market data feed delivered point to point over SoupBinTcp rather than by MoldUdp64 multicast: the same messages, sequenced and replayable from any sequence number.

### Overview

The Odx Pts Itch specification offers two transports for its messages: the point-to-point protocol of SoupBinTcp and the one-to-many protocol of MoldUdp64 (section 2). This is the SoupBinTcp one; the MoldUdp64 one is the Pts protocol.

Because a SoupBinTcp login asks for a sequence number, a client can read the messages a multicast receiver missed from this feed. Odx does not state that the two transports share a session and sequence numbering; they do on Nasdaq's feeds, which Odx's follow.

### Transport

SoupBinTcp: a login names the session and the next sequence number wanted, the server sends every sequenced message from it, heartbeats and end of session.

### Key Characteristics

- **Itch encoded** - The same messages as the multicast Pts feed
- **Tcp delivered** - Reliable ordered delivery as an alternative to multicast
- **Replayable** - A login requests any sequence number of the session

