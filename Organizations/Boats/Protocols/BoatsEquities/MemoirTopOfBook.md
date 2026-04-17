## BoatsEquities Memoir Top Of Book: Boats Best Bid And Offer Data

Real-time top of book feed providing best bid and offer quotations for securities traded on Blue Ocean Ats.

### Overview

Memoir Top Of Book is a unidirectional event-based market data feed that publishes the best bid and best offer for every instrument traded on Blue Ocean Ats. The protocol delivers top of book updates, instrument directory entries, trading session status, trading action notifications, and Reg SHO short sale restriction events. It cannot be used to submit orders.

Messages are encoded using the FIX Trading Community Simple Binary Encoding (Sbe) standard and distributed over the Memx-Udp multicast channel as a sequenced fixed-width stream. A session identifier is issued at the start of the trading day and sequence numbers begin at 1, with an Instrument Directory spin mapping each tradable symbol to a short locate code used for the remainder of the session. Gap fill and snapshot recovery are available over the Memx-Tcp channel for subscribers that miss packets or need to rebuild state.

### Transport

Udp multicast via the Memx-Udp channel for real-time delivery of sequenced Sbe messages, with session identification at start of day and per-message sequence numbers for gap detection. Tcp via the Memx-Tcp channel for gap fill and snapshot recovery when subscribers detect missed messages or need to resynchronize state.

### Key Characteristics

- **Top of book** - Best bid and best offer quotations for every Boats-listed instrument
- **Sbe encoded** - FIX Simple Binary Encoding for fixed-width low-latency parsing
- **Udp multicast delivery** - Real-time publication over the Memx-Udp channel with sequence numbers
- **Tcp recovery** - Gap fill and snapshot recovery over the Memx-Tcp channel
- **Unidirectional** - Market data only, cannot be used to enter orders
- **Instrument directory** - Symbol to locate code mapping published at start of session
- **Trading actions** - Per-instrument trading status notifications
- **Reg SHO** - Short sale restriction status updates for listed securities

