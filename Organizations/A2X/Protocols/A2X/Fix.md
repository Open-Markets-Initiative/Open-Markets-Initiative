## Fix: A2X Markets Fix 4.2 Order Entry and Trade Reporting

Fix 4.2 order entry protocol providing trading Members and third party vendors with order entry, order management, and negotiated trade reporting access to A2X Markets, implemented on Aquis Exchange software.

### Overview

A2X Fix is the order entry interface of A2X Markets, a South African stock exchange that runs on software provided by Aquis Exchange. It is a Fix 4.2 implementation giving trading Members, or third party vendors acting on their behalf, the ability to submit, modify, and cancel orders, and to receive execution reports for fills, cancels, expiries, and rejects throughout the trading day.

Beyond continuous trading, the protocol supports Market at Close (MaC) and Auction on Demand (AoD) order types, iceberg orders with display-quantity refresh, post-only and post-only cancel replace order attributes, and self-trade prevention. It also borrows the Trade Capture Report messages from Fix 4.4 as an extension to the existing 4.2 ports, allowing members to submit Large In Scale crosses, Negotiated Benchmark crosses, and Matched Principal trades for on-exchange reporting.

### Transport

Tcp for authenticated Fix 4.2 sessions carrying order entry, order management, execution reports, and negotiated trade capture reports over a persistent session, with sequence-number gap recovery via Resend Request and Sequence Reset.

### Key Characteristics

- **Fix 4.2** - Industry-standard tagged value order entry protocol over Tcp
- **Order entry and management** - New order single, cancel/replace, cancel, and order cancel reject messages
- **Execution reports** - Acknowledgements, fills, trade busts, restatements, expiries, and rejects
- **Market at Close** - Closing auction order type with lock-time quantity restatement
- **Auction on Demand** - Separate on-demand auction order book with limit and trade-at-middle orders
- **Iceberg orders** - Reserve quantity with display-quantity refresh notified by restatement
- **Post-only order types** - Post-only and post-only cancel replace attributes via custom tag 27010
- **Trade capture reporting** - Fix 4.4 trade capture reports for Large In Scale, Benchmark, and Matched Principal crosses
- **Cancel on disconnect** - Open orders cancelled automatically when the session ends or the connection drops
- **Self-trade prevention** - Optional cancellation of the resting order that would otherwise self-match

