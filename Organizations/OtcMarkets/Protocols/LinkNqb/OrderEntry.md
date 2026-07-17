## LinkNqb Order Entry: OTC Link NQB IDQS FIX order entry

FIX 4.2 order entry interface for OTC Link NQB, OTC Markets Group's inter-dealer quotation system for OTC dealer-quoted equities. Subscribers submit New Order Single, Order Cancel Request, and Order Cancel/Replace Request messages — including market orders — and receive Execution Reports and Order Cancel Rejects. Session-scope codes control when an order is active across pre-market, regular, post-market, and overnight windows.

### Overview

NQB IDQS FIX is the order entry interface for OTC Link NQB. The message vocabulary is the standard FIX 4.2 order lifecycle: New Order Single, Order Cancel Request, Order Cancel/Replace Request inbound; Execution Report and Order Cancel Reject outbound. Market orders are supported alongside priced orders.

Orders carry session-scope codes selecting their active window: P1 (08:00-09:30), P2 (09:30-16:00, equivalent to Day), P3 (16:00-17:00), and PN (20:00-07:45 Sunday through Thursday) — combinable so an order can span pre-market through post-market or run in the overnight session. Order entry price precision is limited to 2 decimal places at or above $1.00.

### Transport

Persistent authenticated FIX 4.2 session over Tcp with standard sequence-number recovery; messages queued prior to initial connection are not delivered.

### Key Characteristics

- **Fix 4.2** - Industry-standard tag-value order entry over an authenticated Tcp session
- **Inter-dealer quotation** - Order entry into the OTC Link NQB IDQS for dealer-quoted OTC equities
- **Session scope codes** - P1/P2/P3 daytime windows plus PN overnight (20:00-07:45 Sunday-Thursday)
- **Market orders** - Market orders supported alongside priced orders
- **Full order lifecycle** - New Order Single, Cancel, Cancel/Replace, Execution Report, and Cancel Reject

