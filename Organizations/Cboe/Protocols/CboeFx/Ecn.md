## CboeFx Ecn: Cboe FX full depth order book feed

Market data feed providing the full depth of the Cboe FX order book, with as many levels as available, over dedicated ITCH sessions.

### Overview

The Cboe FX ITCH Feed provides the full depth of the Cboe FX order book, with as many levels as available. When an Order Modify updates the price of an order, the feed disseminates Cancel Order and New Order messages; a Price Modify message carrying the replaced Order ID, replacing Order ID, Price and Amount was developed to reduce message traffic, to be included in the ITCH feed as well as in the Cboe FX Summary Depth Feed (Summary Depth FAQ, questions 3 and 5).

The Summary Depth Feed delivers three price levels of aggregated depth per pair and the last trade on dedicated ITCH Summary Depth sessions; it cannot be received on an existing ITCH session (Summary Depth FAQ, question 8). Cboe FX ITCH is served from the Equinix NY5 and LD4 matching engines, and the transatlantic service carries ITCH market data from the other site through a local ITCH repeater (Connectivity Manual, sections 1.1 and 2.5).

### Transport

TCP ports for Cboe FX ITCH in NY5 and LD4, by cross-connect in production and by internet in certification; transatlantic market data is distributed via ITCH repeaters in the local data center, to which users connect.

### Key Characteristics

- **Full depth** - Full depth of the order book, with as many levels as available
- **Order messages** - Price changes disseminated as Cancel Order and New Order messages
- **Dedicated sessions** - ITCH sessions, with separate ITCH sessions for Summary Depth
- **Local repeaters** - Transatlantic market data via ITCH repeaters in the local data center
- **NY5 and LD4** - TCP port ranges at both Cboe FX matching engine sites

