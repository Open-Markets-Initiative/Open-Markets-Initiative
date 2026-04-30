## CmeFutures Broker Tec Ust: Cme BrokerTec U.S. Treasury Fixed Income Market Data

Cme BrokerTec U.S. Treasury market data feed distributing price discovery and order book activity for U.S. Treasury benchmark and off-the-run issues traded on the BrokerTec central limit order book. Delivered as SBE messages over UDP multicast with Market By Order Full Depth, Market By Price, and trade statistics channels.

### Overview

BrokerTec U.S. Treasury Market Data carries comprehensive price discovery for the BrokerTec fixed income electronic trading venue, covering the full set of U.S. Treasury actives — 2 Year, 3 Year, 5 Year, 7 Year, 10 Year, 20 Year, and 30 Year benchmark issues — plus off-the-run issues and repo markets. The feed publishes order book depth, trade prints, session statistics, and instrument definition updates, aggregated from the BrokerTec central limit order book.

The feed is carried in Cme's Simple Binary Encoding (SBE) over UDP multicast, using the same Market Data Platform framing as Cme Globex (BinaryPacketHeader with 32-bit packet sequence and 64-bit nanosecond sending time) but with its own channel set and market data configuration service. Subscribers can choose between Market By Order Full Depth (MBOFD) for every order event, Market By Price (MBP) for aggregated price levels, and 50-millisecond conflated channels for bandwidth-sensitive use cases.

Session hours are Sunday 5:30 PM through Friday 4:30 PM Central Time. Recovery follows the standard Cme pattern — missed packets are requested from the TCP market data replay service, and snapshots are refreshed from the market recovery multicast group when needed. Instrument definitions are delivered on a separate channel so subscribers can re-synchronise reference data independently of the incremental feed.

### Transport

Udp multicast for dual-feed A/B delivery of SBE-encoded market data. BrokerTec uses a dedicated Market Data Platform instance separate from Cme Globex, with Market By Order Full Depth (MBOFD), Market By Price (MBP), and 50-millisecond conflated channels. Each datagram begins with the Cme BinaryPacketHeader carrying the packet sequence number and nanosecond sending time. Tcp for market data replay, market recovery snapshots, and instrument / configuration dissemination over the dedicated BrokerTec market data services (incremental schema dissemination and global TCP recovery schema dissemination).

### Key Characteristics

- **U.S. Treasury coverage** - Benchmark 2Y–30Y actives, off-the-run issues, and repo markets on BrokerTec
- **Full depth of book** - Market By Order Full Depth (MBOFD) channel exposes every order event
- **Market By Price** - Aggregated price-level depth feed for bandwidth-sensitive subscribers
- **Conflated channel** - 50-millisecond conflated UDP feed available for reduced message volume
- **SBE over UDP multicast** - Simple Binary Encoding carried over dual-feed UDP multicast for efficient dissemination
- **Packet sequenced** - BinaryPacketHeader packet sequence number and nanosecond sending time for gap detection
- **Dedicated BrokerTec MDP** - Separate Market Data Platform instance and configuration service from Cme Globex
- **TCP replay recovery** - Missed packets recovered via the BrokerTec TCP market data replay service
- **Instrument reference channel** - Separate multicast group delivers instrument definitions and benchmark rolls

