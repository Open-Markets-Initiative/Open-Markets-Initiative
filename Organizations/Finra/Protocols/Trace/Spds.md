## Trace Spds: Securitized Products Dissemination Service

Trace-based trade dissemination service publishing real-time securitized product transaction reports collected under Finra Rule 6700 through the Trade Reporting And Compliance Engine.

### Overview

The Securitized Products Dissemination Service (Spds) is the Finra market data feed that distributes real-time securitized product trade reports submitted through the Trade Reporting And Compliance Engine (Trace). Finra added securitized products to Trace in 2011 under the Finra Rule 6700 Series, and Spds has provided the downstream transparency channel for that data to authorized market data vendors since November 2012.

Spds disseminates Agency Pass-Through and Sba-Backed specified pool transactions, Sba-Backed securities traded To Be Announced, asset backed securities and collateralized mortgage obligations. Transactions in specified pools carry a Reference Data Identifier in place of the Symbol, Cusip and Bsym identifiers, which is why the feed defines a parallel set of Mbs message types alongside the standard ones.

The feed uses the Data Feed Interface (Dfi) message format delivered over MoldUdp64 multicast for real-time distribution, with a companion Tcp re-request service for gap recovery. Subscribers receive fixed-width binary messages covering trade report submission, cancellation, correction, daily price summaries, trading halts and the control messages that frame each operational cycle.

### Transport

Udp multicast over MoldUdp64 carrying sequenced Data Feed Interface messages with per-packet sequence numbers for gap detection and retransmission via the companion re-request service. Tcp for the re-request and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Securitized product trade reports** - Real-time transparency data for US securitized product transactions
- **Trace backed** - Trades sourced from the Finra Trade Reporting And Compliance Engine
- **Parallel Mbs message set** - Specified pool transactions carry a Reference Data Identifier in lieu of Symbol, Cusip and Bsym
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Dfi encoded** - Finra Data Feed Interface binary message format
- **Re-request service** - Tcp-based gap recovery for missed multicast messages
- **Trade lifecycle** - Submission, cancellation, correction, and administrative events
- **Regulated dissemination** - Operated by Finra under Sec-approved transparency rules

