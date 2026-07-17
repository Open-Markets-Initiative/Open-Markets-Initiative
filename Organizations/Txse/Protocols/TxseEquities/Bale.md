## TxseEquities Bale: Txse Binary Top-of-Book Market Data

Real-time top-of-book market data feed publishing best bid and offer, trade prints, symbol/session status, and auction lifecycle events for equities traded on the Texas Stock Exchange. BALE is payload-only; framing and multicast distribution are provided by the RAKE UDP encoding.

### Overview

BALE (best available liquidity ensemble) is the top-of-book market data protocol for the Texas Stock Exchange. It streams best bid/offer updates, trade prints, symbol reference data (DefineSymbol), trading state changes (TradingSessionStatus/SymbolStatus), and the full auction lifecycle (AuctionPreamble/AuctionBandWindow/AuctionPrint) — a compact alternative to full-depth FEED for subscribers that only need aggregated top-of-book plus auction detail.

BALE messages carry only application payload. Message framing, packet-level sequencing, and multicast distribution are handled by the RAKE UDP encoding layer. Gap recovery is not part of BALE itself; subscribers reconnect via the RAKE session layer on TCP for recovery.

### Transport

UDP multicast via RAKE UDP framing for low-latency real-time distribution of sequenced messages with packet-level session/sequence identifiers for gap detection.

### Key Characteristics

- **Top-of-book only** - Best bid and best offer with aggregate size, no per-order detail
- **Auction lifecycle** - Accumulation-period preambles, band-window updates, and cross prints
- **Presence-bit optionals** - Each message declares optional fields via a compact presenceBits bitmap
- **RAKE UDP framing** - Runs over the RAKE UDP encoding for low-latency multicast delivery
- **Equities focused** - Every equity listed on the Texas Stock Exchange

