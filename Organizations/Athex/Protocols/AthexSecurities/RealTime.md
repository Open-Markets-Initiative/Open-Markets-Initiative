## AthexSecurities Real Time: Athens Exchange Securities Market Real Time Channel

The real time channel of the Information Dissemination Service, carrying the fourteen message categories Table 3-3 of the specification lists for the securities market of the Oasis trading system: trades and their cancellations, orders and their cancellations, quotes, indices, instrument summaries, closing prices, projected auction and auction open and projected close prices, high and low limit modifications, instrument states, market statuses, exchange notifications and the four session control messages.

### Overview

The channel is one Tcp stream carrying every market and every financial product of the Oasis platform. The Venue ID of the header names the market publishing a packet and the Message Subcategory names the product, so a consumer of one market reads the stream and filters on the header rather than subscribing to a feed of its own.

A price is nine numeric characters of which the first five, with an optional sign, are the whole part and the last four the decimal one, so a stock price of 15.321 travels as 000153210. A volume is seventeen characters of which the last two are decimal. The specification states these patterns in prose per field rather than in a format column, and the transcription restates each as the pattern its digits make.

Three of the four control messages are their Message Type character and nothing more, so a dispatch to them reads no body. The administrative one carries free text of between one and four hundred characters, which no length field sizes: it runs to the End Of Text that frames the packet.

### Transport

Tcp carries the channel, through the Internet Oriented Communication Portal, which also serves the real time recovery and retransmission features.

### Key Characteristics

- **Category coded dispatch** - A one character Message Category in the shared header selects the body that follows it
- **Fixed width bodies** - Every category but the administrative control message is a width the specification fixes
- **Second level dispatch** - The control message category carries a Message Type of its own, selecting one of four control bodies
- **Counted quote levels** - The quote message repeats a sixty six character bid and ask level as many times as its Quote Levels field states
- **Implied decimals** - Prices carry four decimal places and volumes two, stated by digit pattern and never written on the wire

