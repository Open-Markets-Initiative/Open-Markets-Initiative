## BzxEquities Tcp Depth Of Book: Cboe BZX Tcp Full Depth Of Book Data

Tcp-based full depth of book Pitch feed publishing order events for equities traded on Cboe US Equities BZX Exchange.

### Overview

Tcp Depth Of Book is the Tcp variant of the Cboe BZX Depth Of Book feed, providing the same full order book events delivered over a reliable Tcp connection instead of Ip multicast. It is designed for subscribers that cannot receive multicast feeds directly but still need full depth of book market data.

The message format matches the multicast Pitch feed, so decoders can be shared between the two transports. Because Tcp provides reliable ordered delivery, the Tcp feed does not require a separate gap request service.

### Transport

Tcp for direct Pitch depth of book delivery as an alternative to multicast, providing sequenced reliable delivery without requiring multicast network support.

### Key Characteristics

- **Full depth of book** - Same messages as the multicast Depth Of Book feed
- **Tcp delivered** - Reliable ordered delivery as an alternative to multicast
- **Cboe Pitch** - Native Cboe binary message format
- **No multicast required** - Suitable for network environments without multicast support
- **Session based** - Persistent Tcp session per subscriber

