## NsmEquities NoiView: Nasdaq Stock Market Net Order Imbalance Indicator View

Itch market data feed providing net order imbalance indicator data for Nasdaq Stock Market opening and closing crosses.

### Overview

NoiView delivers real-time net order imbalance indicator information during Nasdaq opening and closing cross periods. The feed reports the paired and imbalance quantities, reference price, and indicative clearing price for each security participating in the cross auction, enabling subscribers to assess supply and demand ahead of the cross execution.

The feed uses Itch binary encoding and is active during pre-open and pre-close periods when the Nasdaq cross auction mechanism is collecting orders. Imbalance updates are disseminated at regular intervals as order flow changes the indicative auction outcome.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Cross auction data** - Paired quantity, imbalance, and indicative prices
- **Opening and closing** - Active during pre-open and pre-close cross periods
- **Real-time updates** - Imbalance recalculated as order flow changes
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
