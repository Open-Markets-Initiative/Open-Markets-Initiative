## TxseEquities Feed: Txse Binary Full-Depth Market Data

Order-by-order full-depth market data feed publishing every add, modify, cancel, and execution event on the Texas Stock Exchange book, plus symbol/session status and auction lifecycle events. FEED is payload-only; framing and multicast distribution are provided by the RAKE UDP encoding.

### Overview

FEED is the full-depth market data protocol for the Texas Stock Exchange, exposing per-order events for complete order book reconstruction. It carries AddOrder, DeleteOrder, ExecuteOrder, ExecuteOrderWithPrice, ModifySizeDown, ReplaceOrder, Trade, and BreakTrade in addition to the shared status messages (TradingSessionStatus, DefineSymbol, SymbolStatus) and auction lifecycle messages (AuctionPreamble, AuctionBandWindow, AuctionPrint).

FEED messages carry only application payload. Message framing, packet-level sequencing, and multicast distribution are handled by the RAKE UDP encoding layer. Subscribers that only need top-of-book with auction detail may prefer BALE, which shares the RAKE UDP transport and message conventions.

### Transport

UDP multicast via RAKE UDP framing for low-latency real-time distribution of sequenced messages with packet-level session/sequence identifiers for gap detection.

### Key Characteristics

- **Order-by-order depth** - Full order book reconstruction from individual add/modify/cancel/execute events
- **Trade prints** - Displayed and non-displayed executions with break support
- **Auction lifecycle** - Accumulation-period preambles, band-window updates, and cross prints
- **Presence-bit optionals** - Status messages declare optional halt-reason fields via a presenceBits bitmap
- **RAKE UDP framing** - Runs over the RAKE UDP encoding for low-latency multicast delivery
- **Equities focused** - Every equity listed on the Texas Stock Exchange

