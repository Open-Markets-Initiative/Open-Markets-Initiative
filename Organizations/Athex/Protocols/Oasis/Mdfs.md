## Oasis Mdfs: Market Data Feed Service

Real time market data for every instrument traded on the Oasis platform, together with Apa over the counter pre-trade and post-trade reports, published as Fix 5.0 Sp2 messages encoded to Fast 1.2 under an incremental and snapshot model, over Udp multicast or Tcp.

### Overview

The service organises market data into groups by venue, instrument type and message type, and each group has an incremental feed and a snapshot feed. A client builds the current state from a snapshot or from retransmission and keeps it with the incremental messages, detecting gaps by Appl Seq Num.

Each version of the service comes with its own templates file, Templates_vN. A file holds up to two templates for each message type, the latest and the one it replaces, so a client can take the new file before the new version of the service is released. The name of a template ends with its id, and ids only increase, so the template with the higher id of a message type is the current one.

The service is designed to Fast 1.2 but uses none of its features, so it is currently backwards compatible with Fast 1.1. After a system recovery that rolls the service back, messages carry an Athex Recovery group in the header recording the rollback.

### Transport

Udp multicast over leased lines, every feed replicated on two identical Sources, A and B, for arbitration, and always Fast encoded. A Tls Fix session per account and Source, carrying the same content as multicast in Fix or Fast encoding, and serving the retransmission and snapshot requests multicast clients also use.

### Key Characteristics

- **Fix 5.0 Sp2** - Fix messages with fields from the extension packs and Athex custom fields
- **Fast 1.2 encoded** - Templates distributed as Xml, using only features compatible with Fast 1.1
- **Versioned templates** - Each templates file carries the current and the previous template of every message
- **Incremental and snapshot** - Each market data group has an incremental feed and a snapshot feed
- **Dual Sources** - Every multicast feed is sent on Sources A and B for arbitration
- **Apa reports** - Over the counter pre-trade and post-trade reports alongside exchange market data

