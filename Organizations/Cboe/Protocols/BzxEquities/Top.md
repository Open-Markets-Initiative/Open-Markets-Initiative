## BzxEquities Top: Cboe BZX Best Bid And Offer Data

Real-time top of book feed publishing best bid and offer quotations and last sale trades for equities traded on Cboe US Equities BZX Exchange.

### Overview

Top is the top of book market data feed for Cboe US Equities BZX Exchange, publishing best bid and best offer updates along with last sale trade reports for every listed equity instrument. It is a lightweight alternative to the full depth of book Pitch feed, designed for subscribers that only need current quotations.

Messages are line-oriented ASCII over a single Tcp connection. There is no multicast distribution; each subscriber connects directly to a Cboe-assigned host and port. Recovery is performed by reconnecting and requesting a spin of the current state.

### Transport

Tcp unicast session to a Cboe-assigned host and port. Messages are fixed-length line-oriented unsequenced ASCII records delimited by newline. Both sides exchange heartbeats once per second; if a spin was requested at logon, the server replays the current top of book for every symbol before delivering live updates.

### Key Characteristics

- **Top of book** - Best bid and best offer for every Cboe US Equities BZX Exchange instrument
- **Tcp unicast** - Single point-to-point Tcp session per subscriber
- **Line-oriented ASCII** - Fixed-length unsequenced messages delimited by newline
- **Trade reports** - Last sale messages published alongside quotes
- **Spin recovery** - Server replays current top of book on logon when requested
- **Trading status** - System event and instrument-level status notifications

