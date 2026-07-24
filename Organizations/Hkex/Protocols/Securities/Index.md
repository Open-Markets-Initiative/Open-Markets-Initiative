## Securities Index: Orion Market Data Cash Index

Hkex Orion Market Data Cash Index publishes real-time and closing values for third-party indices covering securities listed on the Hkex cash market. The feed carries Index Definition messages providing per-index reference data and Index Data messages carrying the current index value, net change from previous close, high/low values, EAS value, turnover, opening/closing values, previous session close, volume, percentage change, and status. Indices are supplied by CSI/CES, HSIL, and S&P.

### Overview

The Index product complements the SS, SP, and SF securities market data feeds by dedicating a separate multicast product to third-party index value publication. Index Definition messages describe each index (code, source, currency); Index Data messages carry the streaming value updates with an index status code identifying real-time, indicative, opening, closing, preliminary close, previous-session close, and stop-loss values.

Index shares the OMD packet header, framing, control, and refresh messages with the SS, SP, and SF products. The Index feed does not carry security-level order book, trade, or reference data messages.

### Transport

Udp multicast delivery on dual A and B channels with per-channel sequence numbers.

### Key Characteristics

- **Index-only feed** - Dedicated to index value publication, no security-level data
- **Third-party indices** - Publishes CSI, CES, HSIL, and S&P index families
- **Index status coded** - Real-time, indicative, opening, closing, preliminary close, previous-session close, stop-loss statuses
- **Turnover and volume** - Aggregated turnover and volume of underlying constituents

