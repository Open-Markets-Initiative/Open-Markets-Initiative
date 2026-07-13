## Output: Koscom Market Data Service Realtime Output feed

Koscom-to-subscriber realtime market data output protocol for the Market Data Service (MDCS). Publishes KRX equity, derivatives, bond, K-OTC, index, and Koscom-originated reference feeds as Exture ASCII fixed-width records over UDP multicast, partitioned into subscription products (Securities A/B/C, Bond A, Derivatives A, Commodities, Index Products 1/2/3, EquityDerivatives, ReferenceInfoInvestorActivities, Koscom).

### Overview

MDCS Realtime Output is Koscom's outbound market data feed distributing Korea Exchange (KRX) real-time trading activity to subscribers of the Market Data Service. Content spans KRX KOSPI, KOSDAQ, and KONEX equities; K200, KOSDAQ150, Equity, KTB, Currency, Commodity futures and options; General and Baby Bonds; REPO; Spot Gold; Emissions; K-OTC; plus KRX Index and Koscom-originated third-party indices (MKF, KIS, KEBI, KABI, NicePNI, WISEfn).

Message dispatch is by two-level TR-CODE — a 2-character Data Category identifies the message family (Quote, Snapshot, Order Filled, Batch Data, Index, Investor Activities, etc.) and a 3-character Information Category identifies the market/product variant (01S KOSPI Equities, 01F Derivatives, 01B Bonds, 000 market-independent, etc.). Subscribers select streams by subscription product; the same content is offered at multiple line-speed tiers.

The Output protocol is realtime-only; historical replay and reference data are distributed through separate Koscom services. Gap detection uses Data Category-specific sequence numbers; recovery is via a companion TCP retransmission service.

### Transport

UDP multicast for real-time delivery of Exture ASCII fixed-width records. Each datagram carries exactly one message, framed by a 2-byte Data Category + 3-byte Information Category TR-CODE prefix and a 0xFF end-of-text sentinel. Streams are partitioned across multicast groups by subscription product and line-speed tier (100M, 45M, 12M, 8M, 512K). TCP retransmission service for gap recovery. Subscribers detect gaps via Data Category-specific sequencing and request replay from the retransmission endpoint.

### Key Characteristics

- **KRX-wide coverage** - Equities, derivatives, bonds, K-OTC, indices, and Koscom-originated reference feeds from all KRX venues
- **Exture ASCII wire format** - Fixed-width printable ASCII records with two-level TR-CODE dispatch and 0xFF end-of-text sentinel
- **Product-partitioned streams** - Multicast groups partition content by subscription product (Securities A/B/C, Bond A, Derivatives A, Commodities, Index Products 1/2/3, EquityDerivatives, ReferenceInfoInvestorActivities, Koscom)
- **Line-tier bandwidth model** - Identical content offered at multiple line-speed tiers (100M, 45M, 12M, 8M, 512K); subscribers select by tier
- **UDP multicast delivery** - One message per UDP datagram over multicast for real-time low-latency distribution
- **TCP retransmission recovery** - Companion TCP retransmission service for gap recovery when subscribers detect missed messages
- **MDCS distribution** - Distributed by Koscom (KRX-owned technology operator) via the MDCS portal at data.koscom.co.kr

