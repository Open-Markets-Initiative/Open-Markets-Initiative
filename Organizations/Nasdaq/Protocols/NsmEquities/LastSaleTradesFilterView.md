## NsmEquities Last Sale Trades Filter View: Nasdaq FilterView, the Nasdaq Last Sale trades of the Nasdaq execution system

Real-time trade data feed from the Nasdaq execution system, the Nasdaq Last Sale (NLS) delivery option without the Nasdaq/FINRA Trade Reporting Facility trades.

### Overview

Nasdaq FilterView is one of the Nasdaq last sale delivery options: it contains the trade data from the Nasdaq execution system only. Nasdaq Last Sale (NLS) adds the Nasdaq/FINRA Trade Reporting Facility (TRF) trades and TRF FilterView carries the TRF trades alone.

The messages are the Nasdaq Last Sale Products messages without the NLS Plus consolidated volume and its end of day trade summary and IPO information messages: a series of sequenced, variable length binary messages of system events, trade reports, trade cancel/error and trade correction messages, and administrative messages. They are offered over MoldUdp64, SoupBinTcp, and SoupBinTcp compressed.

### Transport

Udp multicast via MoldUdp64, a single broadcast channel with A and B feeds and a rerequest service for missed messages. Tcp via SoupBinTcp, plain or compressed, for sequenced delivery of the same messages.

### Key Characteristics

- **Last sale** - Trades from the Nasdaq execution system only
- **Trade lifecycle** - Trade report, trade cancel/error and trade correction messages
- **Administrative messages** - Stock trading action, Reg SHO, stock directory, adjusted closing price, MWCB, IPO quoting period and operational halt messages
- **Nasdaq Itch** - Variable length sequenced binary messages, big endian integers and nanosecond timestamps
- **MoldUdp64 and SoupBinTcp** - MoldUdp64 multicast, SoupBinTcp and compressed SoupBinTcp

