## FinraOrf Tdds: Finra Orf Otc Equity Trade Dissemination

Market data feed publishing real-time over-the-counter equity trade reports collected through the Finra Orf Over The Counter Reporting Facility for non-Nms securities.

### Overview

The Trade Data Dissemination Service (Tdds) is the Finra market data feed for over-the-counter equity transactions in securities that are not Nms stocks. Trade data is collected through the Finra Otc Reporting Facility (Orf) and then published in real time on the Tdds feed so that subscribers, vendors, and downstream systems can see the Otc equity tape as trades are reported.

The feed uses the Data Feed Interface (Dfi) message format delivered over MoldUdp64 multicast for real-time distribution, with a companion Tcp re-request service for gap recovery. Trade submissions, cancellations, corrections, and administrative events are carried as fixed-width binary messages so that subscribers can reconstruct the complete Otc equity trade stream.

### Transport

Udp multicast over MoldUdp64 carrying sequenced Data Feed Interface trade messages with per-packet sequence numbers for gap detection. Tcp for the re-request and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Otc equity trades** - Trade reports for non-Nms securities trading over the counter
- **Orf sourced** - Trades collected through the Finra Otc Reporting Facility
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Dfi encoded** - Finra Data Feed Interface binary message format
- **Re-request service** - Tcp-based gap recovery for missed multicast messages
- **Trade lifecycle** - Submission, cancellation, correction, and administrative events
- **Regulated dissemination** - Operated by Finra under Sec-approved transparency rules

