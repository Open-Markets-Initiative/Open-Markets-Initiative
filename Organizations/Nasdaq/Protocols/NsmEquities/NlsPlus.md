## NsmEquities NlsPlus: Nasdaq Stock Market Nls Plus

Itch market data feed providing last sale data with extended attribution for Nasdaq Stock Market securities.

### Overview

NlsPlus delivers trade reports with additional attribution fields beyond the standard LastSale feed, including market participant identifiers and extended sale condition codes. The feed provides enhanced trade transparency for subscribers requiring detailed execution source information.

The feed uses Itch binary encoding and includes the standard Nsm reference data messages. Each trade report carries the execution price, size, sale conditions, and supplemental attribution fields that identify the reporting market center and trade characteristics.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Extended attribution** - Market participant and trade source identifiers
- **Enhanced sale conditions** - Additional trade characteristic codes
- **Trade reports** - Real-time execution price and size data
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
