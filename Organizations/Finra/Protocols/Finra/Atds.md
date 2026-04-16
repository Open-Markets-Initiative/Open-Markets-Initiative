## Atds: Finra Trace Agency Debt Trade Dissemination

Trace-based trade dissemination service publishing real-time agency debt transaction reports collected under Finra Rule 6700 through the Trade Reporting And Compliance Engine.

### Overview

The Agency Trade Dissemination Service (Atds) is the Finra market data feed that distributes real-time agency debt trade reports submitted through the Trade Reporting And Compliance Engine (Trace). Effective March 1, 2010 Trace expanded to accept trade reports of agency debt transactions as defined in revised Finra Rule 6710, and Atds provides the downstream transparency channel for that data to subscribers and market data vendors.

The feed uses the Data Feed Interface (Dfi) message format delivered over MoldUdp64 multicast for real-time distribution, with a companion Tcp re-request service for gap recovery. Subscribers receive fixed-width binary trade messages including trade report submission, cancellation, correction, and administrative events so they can reconstruct a complete view of the agency debt tape.

### Transport

Udp multicast over MoldUdp64 carrying sequenced Data Feed Interface messages with per-packet sequence numbers for gap detection and retransmission via the companion re-request service. Tcp for the re-request and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Agency debt trade reports** - Real-time transparency data for US agency debt transactions
- **Trace backed** - Trades sourced from the Finra Trade Reporting And Compliance Engine
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Dfi encoded** - Finra Data Feed Interface binary message format
- **Re-request service** - Tcp-based gap recovery for missed multicast messages
- **Trade lifecycle** - Submission, cancellation, correction, and administrative events
- **Regulated dissemination** - Operated by Finra under Sec-approved transparency rules

