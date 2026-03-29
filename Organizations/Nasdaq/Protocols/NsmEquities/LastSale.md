## NsmEquities LastSale: Nasdaq Stock Market Last Sale And Filter View

Itch market data feed providing trade reports and filtered order book views for Nasdaq Stock Market securities.

### Overview

LastSale delivers real-time trade execution reports for all Nsm-listed and Upa securities, including trade price, size, and sale condition information. FilterView extends the last sale data with filtered depth of book information, providing a combined trade and quote feed for subscribers who need both execution and book data.

The feed uses Itch binary encoding and includes the standard Nsm reference data messages. Trade reports carry execution details including match number, sale conditions, and consolidated trade identifiers for regulatory reporting.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Trade reports** - Real-time execution price, size, and sale conditions
- **FilterView** - Optional filtered depth of book alongside trade data
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
- **Consolidated trade identifiers** - Match numbers for regulatory and audit purposes
