## Trace Btds: Bond Trade Dissemination Service

Trace-based trade dissemination service publishing real-time last sale data for over the counter corporate bond transactions collected under Finra Rule 6700 through the Trade Reporting And Compliance Engine.

### Overview

The Bond Trade Dissemination Service (Btds) is the Finra market data feed that distributes real-time last sale price and related trade data for United States dollar denominated investment grade and high yield corporate bonds. Under Finra Rule 6700 all member firms are required to report trades in eligible corporate bonds into the Trade Reporting And Compliance Engine (Trace), and Btds is the downstream transparency channel that carries those reports to authorized market data vendors and direct subscribers.

The feed uses the Data Feed Interface (Dfi) message format delivered over MoldUdp64 multicast. Every message opens with a twenty four byte header carrying the message category, message type, trade identifier, market center originator and a fourteen byte Eastern Time date and time stamp. Trade, administrative and control message categories carry trade reports, cancels and corrections, daily trade summaries, trading halts and end of day market aggregate statistics.

Btds carries data sourced from the Cusip Service Bureau, so a firm must hold a Cusip daily licensing agreement to receive the direct feed product. Finra operates the service through its technical service provider Nasdaq, which runs the Multi Product Platform infrastructure shared with the other Finra transparency feeds.

### Transport

Udp multicast over MoldUdp64 carrying sequenced Data Feed Interface messages with per-packet sequence numbers for gap detection, broadcast as primary and back-up groups from the New York Metro and Mid-Atlantic Metro data centers. Tcp for the re-request service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Corporate bond trade reports** - Real-time transparency data for United States corporate bond transactions
- **Trace backed** - Trades sourced from the Finra Trade Reporting And Compliance Engine
- **Investment grade and high yield** - Covers investment grade and high yield corporate bonds, church bonds and equity linked notes
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Dfi encoded** - Finra Data Feed Interface fixed width Ascii message format
- **Market aggregates** - End of day market breadth and market sentiment statistics disseminated after 6:30pm Eastern
- **Cusip licensed** - Direct feed receipt requires a Cusip daily licensing agreement

