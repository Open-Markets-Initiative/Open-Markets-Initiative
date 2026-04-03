## Cboe Cfe Futures Depth Of Book

Pitch multicast feed providing full order-level depth of book for Cboe Futures Exchange.

### Overview

Futures Depth Of Book delivers real-time order-by-order market data for contracts traded on Cboe Futures Exchange. The feed shows individual order add, modify, and cancel activity, enabling subscribers to reconstruct the full limit order book for each futures contract.

The feed covers all listed futures contracts including Vix futures and other volatility products. Messages include order priority information, execution reports, and contract-level trading status updates.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Order-level granularity** - Individual order activity for full book reconstruction
- **Vix futures coverage** - Data for Vix and other volatility index futures
- **Real-time executions** - Trade messages with price, quantity, and condition codes
- **Sequenced multicast** - Sequence numbers on all messages for gap detection
