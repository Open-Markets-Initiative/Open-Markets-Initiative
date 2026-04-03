## Cboe Edga Equities Etf Implied Liquidity

Pitch feed providing synthetic depth of book for Etf instruments derived from underlying component liquidity.

### Overview

Equities Etf Implied Liquidity constructs a synthetic order book for Etf instruments by calculating implied prices and quantities from the real-time liquidity of each underlying component security. The feed enables participants to see executable depth beyond what is resting on the Etf order book itself.

The implied book reflects the theoretical Etf price at which a creation or redemption basket could be assembled from available component liquidity. This provides Etf market makers and arbitrageurs with a real-time view of implied fair value and tradeable depth.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Synthetic depth** - Implied Etf book derived from underlying component liquidity
- **Real-time calculation** - Continuously updated as component book changes occur
- **Arbitrage support** - Enables Etf creation and redemption fair value assessment
- **Component-based** - Reflects aggregate executable depth across basket constituents
