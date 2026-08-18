## CixAspen Order Entry: CIX ATS1 Fix 4.2 Order Entry

Fix 4.2 order entry protocol for submitting, replacing, and cancelling orders on the CIX ATS, with fills and order status returned via Execution Reports. A single order entry gateway routes to any of the three CIX books via ExDestination(100).

### Overview

CIX Fix is the order entry interface of the CIX ATS, operated by CIX Trading Inc. It is a Fix 4.2 implementation letting members submit, modify, and cancel orders and receive execution reports for fills, cancels, restatements, and rejects throughout the trading day. A single order entry session reaches all three CIX books - CIX ASPEN, CIX ASPEN VERT, and CIX MIDPOINT - with the destination book selected per order via ExDestination(100).

The destination book is selected per order with ExDestination(100): ASPC routes to the CIX ASPEN lit book, ASPV to the CIX ASPEN VERT lit book, and INCC to the CIX MIDPOINT dark book. The protocol supports market, limit, and pegged (midpoint, primary passive, and market aggressive) order types, iceberg orders with randomized display refresh, minimum acceptable quantity, post-only add-liquidity, and self-trade prevention, together with the UMIR regulatory tags required for Canadian order marking and trade reporting.

### Transport

Tcp for authenticated Fix 4.2 sessions carrying order entry, cancel, cancel/replace, execution reports, and order cancel rejects over a persistent session, with sequence-number gap recovery via Resend Request and Sequence Reset.

### Key Characteristics

- **Fix 4.2** - Industry-standard tagged value order entry protocol over Tcp
- **Order entry and management** - New order single, cancel/replace, cancel, and order cancel reject messages
- **Execution reports** - Acknowledgements, fills, cancels, restatements, and rejects
- **Pegged order types** - Midpoint, primary passive, and market aggressive peg orders
- **Iceberg orders** - Reserve quantity with static or randomized display-quantity refresh
- **Minimum quantity** - Minimum acceptable quantity with optional contra-side aggregation
- **Self-trade prevention** - Cancel newest, cancel oldest, decrement and cancel, or execute-and-suppress
- **UMIR regulatory marking** - Canadian account type, user id, and UMIR designation tags for order marking and trade reporting
- **Book routing** - Destination book selected per order via ExDestination(100): ASPC (CIX ASPEN), ASPV (CIX ASPEN VERT), INCC (CIX MIDPOINT)

