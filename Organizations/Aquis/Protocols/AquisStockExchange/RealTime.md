## AquisStockExchange Real Time: Aquis Stock Exchange real time market data

Binary real time market data feed of the Aquis Market Data (Amd) protocol, publishing the orders, market maker quotes, trades, trade reports and auction events of securities traded on Aquis Stock Exchange via Ip multicast.

### Overview

The real time feed publishes Order Add, Order Modify, Order Cancel, Quote Add/Replace, Quote Cancel, Trade, Trade Report, Trade Report Modify, Trade Report Cancel and Trade Bust messages, and AoD Update during an Auction on Demand (section 2.1).

Tick Table Data, Security Definition and Trader Definition messages identify the securities, tick tables and quote originators before the market opens; Security Status messages publish trading status changes and Security Statistics the opening and closing prices. Each message carries the feed's sequence number for the day.

### Transport

Ip multicast feeds, WAN-shaped and Gig-shaped, from more than one channel, each packet a message count then its messages; a Heartbeat is sent after one second with no trading data.

### Key Characteristics

- **Market maker quotes** - Quote Add/Replace and Quote Cancel messages, each naming the market maker by a trader ID the Trader Definition messages define
- **Trade reports** - Trade Report, Trade Report Modify and Trade Report Cancel messages for off book trades members report
- **Auction On Demand** - AoD Update messages during continuous trading

