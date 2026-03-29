## Cboe Options Market Data Feed

Csm streaming market data feed providing real-time options quotes, trades, and book updates for Cboe Options Exchange.

### Overview

Options Market Data Feed delivers comprehensive real-time market data for options series traded on Cboe Options Exchange using the Csm protocol. The feed provides quotes, trades, and book updates for individual options series.

The feed is the primary Csm-based source for options market data, serving participants who consume Cboe options pricing through the Csm delivery framework. It covers all listed series with quote, trade, and instrument status information.

### Transport

Udp multicast delivery organized by product group with recovery mechanisms for gap handling.

### Key Characteristics

- **Csm protocol** - Streaming market data using the Csm message encoding framework
- **Quotes and trades** - Real-time quote updates and trade execution reports
- **Full series coverage** - All listed options series on Cboe Options Exchange
- **Product group organization** - Multicast groups organized by options class and venue
