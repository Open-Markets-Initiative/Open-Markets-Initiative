## NsmEquities Last Sale: Nasdaq Last Sale (NLS)

Real-time trade data feed from the Nasdaq execution system and the Nasdaq/FINRA Trade Reporting Facilities, with Nasdaq FilterView and TRF FilterView subsets.

### Overview

Nasdaq Last Sale (NLS) is a direct data feed of real-time trade data from the Nasdaq execution system and the Nasdaq/FINRA Trade Reporting Facilities (TRFs). Nasdaq FilterView carries only the Nasdaq execution system trades and TRF FilterView only the TRF trades; NLS Plus adds the Nasdaq Texas and PSX trades with consolidated volume and is a separate protocol.

The messages are a series of sequenced, variable length binary messages: system events, trade reports, trade cancel/error and trade correction messages, and administrative messages. They are offered over MoldUdp64, SoupBinTcp, and SoupBinTcp compressed.

### Transport

Udp multicast via MoldUdp64, a single broadcast channel with A and B feeds and a rerequest service for missed messages. Tcp via SoupBinTcp, plain or compressed, for sequenced delivery of the same messages.

### Key Characteristics

- **Last sale** - Trades from the Nasdaq execution system and the Nasdaq/FINRA TRFs
- **Trade lifecycle** - Trade report, trade cancel/error and trade correction messages
- **Administrative messages** - Stock trading action, Reg SHO, stock directory, adjusted closing price, MWCB, IPO quoting period and operational halt messages
- **Nasdaq Itch** - Variable length sequenced binary messages, big endian integers and nanosecond timestamps
- **MoldUdp64 and SoupBinTcp** - MoldUdp64 multicast, SoupBinTcp and compressed SoupBinTcp

