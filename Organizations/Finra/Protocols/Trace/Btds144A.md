## Trace Btds144A: Bond Trade Dissemination Service for 144A Transactions

Trace-based trade dissemination service publishing real-time last sale data for over the counter corporate bond transactions executed under Securities Act Rule 144A and collected under Finra Rule 6700 through the Trade Reporting And Compliance Engine.

### Overview

The Bond Trade Dissemination Service for 144A Transactions (Btds144A) is the Finra market data feed that distributes real-time last sale price and related trade data for corporate bonds sold under Securities Act Rule 144A. Rule 144A permits the resale of restricted securities to qualified institutional buyers without registration, and Finra began disseminating transaction data for Trace eligible 144A corporate debt on a separate channel so that this institutional market is reported apart from the registered corporate bond tape carried on Btds.

The feed uses the Data Feed Interface (Dfi) message format delivered over MoldUdp64 multicast. Every message opens with a twenty four byte header carrying the message category, message type, trade identifier, market center originator and a fourteen byte Eastern Time date and time stamp. Trade, administrative and control message categories carry trade reports, cancels and corrections, daily trade summaries, trading halts and end of day market aggregate statistics, in message formats identical to those of Btds.

Btds144A carries data sourced from the Cusip Service Bureau, so a firm must hold a Cusip daily licensing agreement to receive the direct feed product. Finra operates the service through its technical service provider Nasdaq, which runs the Multi Product Platform infrastructure shared with the other Finra transparency feeds.

### Transport

Udp multicast over MoldUdp64 carrying sequenced Data Feed Interface messages with per-packet sequence numbers for gap detection, broadcast as primary and back-up groups from the New York Metro and Mid-Atlantic Metro data centers. Tcp for the re-request service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Rule 144A trade reports** - Real-time transparency data for United States corporate bond transactions executed under Securities Act Rule 144A
- **Trace backed** - Trades sourced from the Finra Trade Reporting And Compliance Engine
- **Qualified institutional buyers** - Covers restricted securities resold to qualified institutional buyers rather than registered public issues
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Dfi encoded** - Finra Data Feed Interface fixed width Ascii message format
- **Market aggregates** - End of day market breadth and market sentiment statistics disseminated after 6:30pm Eastern
- **Cusip licensed** - Direct feed receipt requires a Cusip daily licensing agreement

