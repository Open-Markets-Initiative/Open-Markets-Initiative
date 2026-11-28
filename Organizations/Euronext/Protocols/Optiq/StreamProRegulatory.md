## Optiq Stream Pro Regulatory: Euronext Stream Pro Sbe Regulatory Feed

Sbe-encoded EU and UK MiFID II pre-trade and post-trade transparency data for Euronext cash and derivatives markets delivered through Kafka topics.

### Overview

The Euronext Stream Pro regulatory feed publishes EU and UK MiFID II transparency data in the Esma formats: Rts1 pre-trade and post-trade transparency for equities and Rts2 post-trade transparency for non-equities, each on its own Kafka topics.

It shares the Stream Pro framing: each Kafka message carries one Optiq Market Data Packet of complete Sbe messages, optionally Lz4 compressed.

### Transport

Kafka topics over the internet, one Market Data Packet per Kafka message.

### Key Characteristics

- **MiFID II transparency** - Rts1 pre and post trade, Rts2 post trade
- **Kafka delivery** - Dedicated regulatory topics
- **Esma formats** - Prices, quantities and times as Esma text fields

