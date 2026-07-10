## LinkAts Multicast: OTC Markets Multicast Data Feeds — quote-based binary market data

Daytime binary multicast market data feed for OTC Link ATS, publishing quote, inside, reference price, trade, and security status events across the full OTC Markets universe (OTCQX, OTCQB, OTCID, Pink, Expert Market). A single multicast product bundles all channel content (Quote, Quote Update, Inside, Inside Update, Reference Price, Extended Security, Trade, Extended Trade, Trade Status). Recovery via A/B feed arbitration plus gap-fill and snapshot services.

### Overview

OTC Markets Multicast is the daytime market data feed for OTC Link ATS, distributing real-time quotations, trade reports, and reference data for securities across the OTCQX, OTCQB, OTCID, Pink, and Expert Market tiers. The wire vocabulary is quote-based: individual dealer quote add/update/delete events plus aggregated Inside (top-of-book) events, extended security metadata, and last-sale trade reports.

The protocol bundles all channels (quote, inside, reference price, trade, security status) into a single multicast product rather than splitting per-channel like the overnight feeds. Recovery uses A/B feed arbitration for real-time redundancy plus a TCP replay/resend service for gap fills and mid-day snapshots.

### Transport

UDP multicast for real-time delivery of sequenced binary quote and trade messages. Each packet carries a header with sequence number, packet flag, and message count, followed by concatenated message records framed by a 3-byte message header (MessageSize + MessageType). Redundant A/B multicast feeds for arbitration. TCP-based recovery services: Replay Request for gap fill and Resend Request Ack for snapshot recovery when subscribers detect missed messages on the multicast feed.

### Key Characteristics

- **Full OTC Markets coverage** - Real-time quotes and trades for OTCQX, OTCQB, OTCID, Pink, and Expert Market securities
- **Quote-based vocabulary** - Individual dealer quote add/update/delete events plus aggregated Inside top-of-book
- **Extended security metadata** - Reference data including CUSIP, tier, market maker identity, and trading status
- **A/B multicast redundancy** - Redundant A and B feeds for arbitration and gap detection
- **TCP replay recovery** - Replay Request for gap fill and Resend Request Ack for snapshot recovery
- **Single-channel delivery** - All content bundled on one multicast product rather than split across dedicated channels

