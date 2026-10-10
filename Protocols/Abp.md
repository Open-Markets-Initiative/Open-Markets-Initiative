## Abp: NYSE Arca Binary Protocol

Legacy binary market data encoding carrying the Nyse Bonds trade and depth of book feeds over a single Tcp session, predating the Pillar platform.

### Overview

The Arca Binary Protocol is the framing behind the Nyse Bonds Trades and Depth of Book feeds. The two documents name the same four byte framing differently - the Trades specification calls it the "NYSE ArcaTrade Standard Header" and the Depth of Book specification the "NYSE ArcaBook Standard Message Header" - and the Trades specification refers to its own messages as ArcaBook messages throughout, so one encoding covers both. Unusually, the two directions are framed differently: messages the exchange sends carry a four byte header of a two byte body length, a one byte Ascii message type and one padding byte, while messages the client sends are Ascii and terminated by an ETX character with no header at all.

Application message bodies are fixed length and big endian. Prices are four byte integers paired with a Price Scale Code, which names the power of ten to divide by; the code is itself an Ascii character rather than a binary value, as are the Auction Time fields. Timestamps are four byte counts of milliseconds since midnight of the trading day.

Bonds are identified either by a Nyse Arca specific symbol or by Cusip or Isin, and the Cusip and Isin field is left null unless the subscriber has requested the data and holds the licence for it.

### Transport

A single authenticated Tcp session. The client logs in with a username, password and a starting sequence number, then receives sequenced application messages until it logs off. Recovery is by replay from a requested sequence number rather than by multicast arbitration.

### Key Characteristics

- **Session oriented** - One authenticated Tcp session with login, heartbeat and logoff
- **Asymmetric framing** - Server messages are headered binary, client messages are ETX terminated Ascii
- **Fixed length bodies** - Every application message body is a fixed size the header counts exactly
- **Scaled prices** - Integer prices divided by a power of ten named in an Ascii Price Scale Code
- **Sequence replay** - Recovery by logging in from a chosen sequence number rather than retransmission requests
- **Licensed identifiers** - Cusip and Isin disseminated only to subscribers holding the licence

