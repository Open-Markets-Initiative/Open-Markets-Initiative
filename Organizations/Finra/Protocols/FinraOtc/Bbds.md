## FinraOtc Bbds: Finra Otc Bulletin Board Quote Dissemination

Market data feed publishing quotations and administrative messages from the Otc Bulletin Board for securities that trade over the counter.

### Overview

The Bulletin Board Dissemination Service (Bbds) is the Finra data feed that publishes quotations and administrative messages from the Otc Bulletin Board (Otcbb). It delivers quote updates, inside quotation changes, security status messages, closing process notifications, and related administrative events needed by subscribers to track bulletin board activity through the trading day.

The feed is delivered as a sequenced Data Feed Interface (Dfi) stream with fixed-width binary messages, distributed via Udp multicast for real-time performance and backed by a Tcp re-request service for gap recovery. Subscribers receive a complete picture of the Otcbb state without needing to aggregate separate inputs.

### Transport

Udp multicast carrying sequenced Data Feed Interface messages for real-time quote dissemination, with per-packet sequence numbers for gap detection. Tcp for the re-request service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Otc Bulletin Board** - Quotations for securities trading through the Otcbb
- **Inside quotations** - Best bid and offer summaries for listed Otcbb securities
- **Dfi encoded** - Finra Data Feed Interface binary message format
- **Multicast delivery** - Real-time Udp multicast distribution of quote events
- **Re-request service** - Tcp-based gap recovery for missed multicast messages
- **Administrative messages** - Closing process and security status notifications
- **Regulated dissemination** - Operated by Finra under Sec-approved transparency rules

