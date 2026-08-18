## Lse Analytics: Analytics

Analytics service publishing order book activity statistics for London Stock Exchange instruments over the Group Ticker Plant.

### Overview

Analytics is the Lseg Group Ticker Plant derived statistics service for London Stock Exchange. The Analytics message summarises order book activity over an explicit calculation window, reporting the number and cumulative size of buy and sell orders received, cancellation counts broken down by limit and market order, and the bid ask spread at the time of publication.

It also reports volume weighted average price separately for trades triggered by an aggressing buy order and by an aggressing sell order, calculated over trades executed in continuous trading within the window.

### Transport

Udp multicast using the Lseg Group Ticker Plant unit header framing for real time delivery of sequenced binary messages. Tcp for the Group Ticker Plant replay and recovery services used to recover missed multicast messages.

### Key Characteristics

- **Calculation window** - Each message reports the start and end time of the window it summarises
- **Order flow counts** - Buy and sell order counts, sizes and cancellations within the window
- **Spread and vwap** - Bid ask spread at publication and vwap split by aggressing side

