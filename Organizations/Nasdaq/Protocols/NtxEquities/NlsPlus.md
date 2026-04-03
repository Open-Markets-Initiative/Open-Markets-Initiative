## NtxEquities NlsPlus: Nasdaq Ntx Nls Plus

Itch market data feed providing last sale data with extended attribution for Nasdaq Ntx securities.

### Overview

NlsPlus delivers trade reports with additional attribution fields for Ntx-listed securities, including market participant identifiers and extended sale condition codes. The feed provides enhanced trade transparency beyond standard last sale reporting.

The feed uses Itch binary encoding and includes the standard Ntx reference data messages. Each trade report carries the execution price, size, sale conditions, and supplemental attribution fields.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Extended attribution** - Market participant and trade source identifiers
- **Enhanced sale conditions** - Additional trade characteristic codes
- **Trade reports** - Real-time execution price and size data
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
