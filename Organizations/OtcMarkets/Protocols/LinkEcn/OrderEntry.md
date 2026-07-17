## LinkEcn Order Entry: OTC Link ECN FIX order entry

FIX 4.2 order entry interface for OTC Link ECN, OTC Markets Group's SEC registered alternative trading system providing anonymous electronic order matching for OTC equity securities. Subscribers submit New Order Single, Order Cancel Request, and Order Cancel/Replace Request messages for firm, automatically executable orders and receive Execution Reports and Order Cancel Rejects. Session-scope codes control when an order is active across pre-market, regular, and post-market windows.

### Overview

OTC Link ECN FIX is the order entry interface for OTC Link ECN. The message vocabulary is the standard FIX 4.2 order lifecycle: New Order Single, Order Cancel Request, Order Cancel/Replace Request inbound; Execution Report and Order Cancel Reject outbound. Orders are anonymous and firm, matched automatically by the ECN.

Orders carry session-scope codes selecting their active window: P1 (08:00-09:30), P2 (09:30-16:00, equivalent to Day), and P3 (16:00-17:00) — combinable so an order can span pre-market through post-market. Market orders are documented but not yet available. Order entry price precision is limited to 2 decimal places at or above $1.00.

### Transport

Persistent authenticated FIX 4.2 session over Tcp with standard sequence-number recovery; messages queued prior to initial connection are not delivered.

### Key Characteristics

- **Fix 4.2** - Industry-standard tag-value order entry over an authenticated Tcp session
- **Anonymous ECN matching** - Firm, automatically executable orders matched anonymously for OTC equities
- **Session scope codes** - P1/P2/P3 windows spanning pre-market (08:00) through post-market (17:00)
- **Full order lifecycle** - New Order Single, Cancel, Cancel/Replace, Execution Report, and Cancel Reject
- **Price precision rules** - Up to 2 decimal places at or above $1.00, finer precision below

