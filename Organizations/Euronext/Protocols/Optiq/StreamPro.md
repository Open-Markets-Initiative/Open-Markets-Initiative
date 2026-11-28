## Optiq Stream Pro: Euronext Stream Pro Sbe Market Data

Sbe-encoded market data for Euronext cash and derivatives markets delivered through Kafka topics, carrying full order book, best bid and offer, reference data and trades.

### Overview

Euronext Stream Pro is the Kafka-delivered market data service for Euronext's Optiq cash and derivatives markets. Clients consume real-time and snapshot channels from Kafka topics split by asset class, country of issue, currency and pack: Full Order Book Market Update (FBMU), Best Bid and Offer (BBBO), and Reference Data and Full Trade Information (REFT).

Each Kafka message carries one Optiq Market Data Packet: a packet header with time, sequence number, flags and channel, then complete Sbe messages, each led by a frame length and an Sbe header. A packet body may be Lz4 compressed, flagged in the packet header.

### Transport

Kafka topics over the internet, one Market Data Packet per Kafka message, for real-time and snapshot channels.

### Key Characteristics

- **Kafka delivery** - Topics consumed over the internet with an Api key
- **Sbe encoded** - Optiq market data packet framing with Sbe messages
- **Data packs** - Full order book, best bid and offer, reference data and trades
- **Snapshot channels** - Periodic unsolicited snapshots on dedicated topics
- **Lz4 compression** - Packet bodies optionally Lz4 block compressed

