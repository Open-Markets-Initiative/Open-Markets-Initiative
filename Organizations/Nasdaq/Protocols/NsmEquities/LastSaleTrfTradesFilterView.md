## NsmEquities Last Sale Trf Trades Filter View: TRF FilterView, the Nasdaq Last Sale trades of the Nasdaq/FINRA Trade Reporting Facilities

Real-time trade data feed from the Nasdaq/FINRA Trade Reporting Facilities (TRFs), the Nasdaq Last Sale (NLS) delivery option without the Nasdaq execution system trades.

### Overview

TRF FilterView is one of the Nasdaq last sale delivery options: it contains the trade data from the Nasdaq/FINRA Trade Reporting Facilities (TRFs), Carteret and Chicago, only. Nasdaq Last Sale (NLS) adds the Nasdaq execution system trades and Nasdaq FilterView carries the Nasdaq execution system trades alone.

The messages are the Nasdaq Last Sale Products messages without the NLS Plus consolidated volume and its end of day trade summary and IPO information messages, and without the stock trading action, IPO quoting period update and operational halt messages, which are not included on TRF FilterView. They are offered over MoldUdp64, SoupBinTcp, and SoupBinTcp compressed.

### Transport

Udp multicast via MoldUdp64, a single broadcast channel with A and B feeds and a rerequest service for missed messages. Tcp via SoupBinTcp, plain or compressed, for sequenced delivery of the same messages.

### Key Characteristics

- **Last sale** - Trades from the Nasdaq/FINRA TRF Carteret and TRF Chicago only
- **Trade lifecycle** - Trade report, trade cancel/error and trade correction messages, with the TRF reported client timestamp
- **Administrative messages** - Reg SHO, stock directory, adjusted closing price and MWCB messages
- **Nasdaq Itch** - Variable length sequenced binary messages, big endian integers and nanosecond timestamps
- **MoldUdp64 and SoupBinTcp** - MoldUdp64 multicast, SoupBinTcp and compressed SoupBinTcp

