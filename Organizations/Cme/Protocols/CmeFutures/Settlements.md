## CmeFutures Settlements: Cme End Of Day Settlement Data

End-of-day settlement price and open interest feed publishing official settlement data for futures and options traded on Cme Globex.

### Overview

Cme Settlements is the end-of-day market data product that publishes official settlement prices, open interest figures, and settlement-related events for futures and options traded on Cme Globex. It is the authoritative source for mark-to-market pricing and clearing calculations, distributed as a separate product from the intraday Mdp3 feed.

The settlements feed uses the same Sbe wire format as Mdp3 and is available over Udp multicast for real-time distribution plus Tcp session management for recovery. Consumers include clearing members, risk systems, post-trade infrastructure, and data vendors.

### Transport

Udp multicast for distribution of Sbe-encoded settlement price and open interest messages at end of day. Tcp for recovery of end-of-day settlement data via the Cme session management service.

### Key Characteristics

- **Settlement prices** - Official mark-to-market prices for Cme futures and options
- **Open interest** - End-of-day open interest figures per instrument
- **Sbe encoded** - Consistent with Mdp3 wire format
- **Multicast delivery** - Udp multicast distribution of settlement data
- **Tcp recovery** - Session management service for historical retrieval
- **Clearing source** - Authoritative data for clearing and risk calculations

