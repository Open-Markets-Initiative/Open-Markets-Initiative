## CmeFutures Streamlined: Cme Globex Streamlined Top Of Book Data

Sbe-encoded lightweight top of book market data feed publishing best bid and offer quotations for futures and options traded on Cme Globex.

### Overview

Cme Streamlined is a lightweight market data product that publishes best bid and offer quotations plus last sale trade reports for futures and options traded on Cme Globex, delivered in the Cme Sbe binary format. It is positioned as a bandwidth-efficient alternative to the full Mdp3 feed for subscribers that only need top of book information.

The feed shares the A and B channel redundancy model and the Sbe wire format of Mdp3, so clients can share decoder infrastructure. Tcp-based recovery is available through the same Cme session management service used for Mdp3 recovery.

### Transport

Udp multicast for real-time delivery of sequenced Sbe streamlined top of book messages with A and B channel redundancy. Tcp for recovery via the Cme session management service.

### Key Characteristics

- **Top of book** - Best bid and offer for Cme Globex instruments
- **Lightweight** - Bandwidth-efficient alternative to Mdp3
- **Sbe encoded** - Consistent with Mdp3 wire format
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Tcp recovery** - Cme session management service for gap fill

