## BrokerTec: Cme BrokerTec Us Treasury Market Data

Sbe-encoded market data feed for BrokerTec Us Treasury fixed income trading on the Cme Globex platform.

### Overview

The Cme BrokerTec Ust feed delivers real-time market data for Us Treasury securities traded on the BrokerTec platform, which Cme Group acquired from Nex Group in 2018. The feed provides depth of book (bids and offers), trade reports, and reference data for on-the-run and off-the-run Treasury benchmarks.

Messages include MdIncrementalRefreshBtec with fields for price, size, price level, traded volume, symbol, maturity date, Cusip, coupon rate, and trade condition (hit/take). The protocol uses the same Sbe encoding framework as other Cme market data feeds.

### Transport

Udp multicast with Sbe-encoded messages. Same packet structure and dual-feed architecture as Mdp 3.0.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields with little-endian byte ordering
- **Fixed income focused** - Us Treasury securities with Cusip, maturity date, and coupon rate fields
- **Depth of book** - Bid, offer, and trade entries with price level information
- **Trade conditions** - Hit (H) and Take (T) trade condition indicators
- **Yield pricing** - Price type field supporting yield-based pricing
- **Nanosecond timestamps** - Transaction time in nanoseconds since Unix epoch
