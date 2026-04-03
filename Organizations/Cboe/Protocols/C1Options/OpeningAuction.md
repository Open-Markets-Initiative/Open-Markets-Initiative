## Cboe Options Opening Auction

Csm feed providing pre-market opening auction indicative data for options series on Cboe Options Exchange.

### Overview

Options Opening Auction delivers pre-market auction indicative information for options series traded on Cboe Options Exchange using the Csm protocol. The feed provides expected opening prices, paired quantities, and imbalance data during the pre-opening collection period.

The feed serves participants who monitor and participate in the options opening process. Indicative data is continuously refreshed as order interest accumulates before the opening rotation, providing visibility into expected opening conditions for each series.

### Transport

Udp multicast delivery organized by product group with recovery mechanisms for gap handling.

### Key Characteristics

- **Pre-market data** - Indicative prices and quantities before the opening rotation
- **Csm protocol** - Delivered using the Csm streaming market data framework
- **Continuous refresh** - Updated indicative data as pre-opening interest changes
- **Imbalance visibility** - Paired and unpaired quantities during the collection period
