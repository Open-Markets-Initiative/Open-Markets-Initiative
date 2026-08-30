## Itac Market Data: Market Data

Order by order market data feed for every market carried on the Jse Integrated Trading and Clearing platform, publishing add, modify, execute and delete events alongside instrument reference data, statistics and exchange news.

### Overview

The feed carries the Jse equity and derivative markets and the Namibian Stock Exchange equity market from one gateway. It is load balanced by market data group rather than by market: each instrument belongs to exactly one group for the whole day, and the Symbol Directory messages on a group's real time channel are what tell a recipient which instruments it carries.

The group also selects the market, and that is the one place the wire format varies. Symbol Directory is published in two layouts under the same message type: the equity markets end the message after Corporate Action, while the derivative markets append leg symbols, contract multiplier, settlement method, instrument sub category and exercise style. Nothing inside the message distinguishes them, so a recipient tells them apart by the message length or by the group it subscribed to.

Jse encodes the per message length in two bytes where the Lseg Millennium feed this protocol descends from uses one, making the Jse message header three bytes rather than two. The unit header framing is otherwise identical, which is why the two share the Mitch encoding but not a header definition.

Prices are eight byte integers with eight implied decimal places, except Turnover, Notional Exposure and Notional Delta Exposure on the Extended Statistics message, which carry four. Statistics fields that are unset or withdrawn are published as negative values rather than omitted, other than Volume and Number of Trades which go to zero.

There is no heartbeat message. A unit header with a message count of zero serves that purpose, and because it carries no message it does not advance the real time channel sequence number.

### Transport

Udp multicast carrying Mitch binary messages under a unit header, with per packet sequence numbers for gap detection and a primary and secondary channel per market data group for arbitration. Tcp to the replay and recovery channels, replay retransmitting a numbered range of messages missed on the multicast feed and recovery serving order book, instrument, trade, statistics and news snapshots for initialising state.

### Key Characteristics

- **Order by order** - Add, modify, execute and delete events for each individual order
- **One feed, every market** - Jse equity and derivative markets and the Nsx equity market from a single gateway
- **Load balanced by group** - Each instrument is assigned to one market data group for the whole trading day
- **Throttled and un-throttled** - The same services on both gateways, differing only in output rate
- **Options analytics** - Extended Statistics carries theoretical price, delta, gamma, vega, theta, rho and volatility
- **Top of book** - A price level view for recipients that do not maintain an order by order book

