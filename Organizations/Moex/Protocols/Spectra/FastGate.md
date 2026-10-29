## Spectra Fast Gate: FAST Gate

The Spectra derivatives market's Fix Fast multicast market data, publishing trades, order books, market fundamentals, instruments and their status, trading session status, indexes, news and the anonymous orders log as Fix messages encoded to Fast 1.1, the legacy feed SIMBA is superseding.

### Overview

Fast Gate distributes the data of the Spectra trading system and the Moscow Exchange index replica, for the Moscow Exchange and for the Eurasian Trade System Commodity Exchange, each organisation with templates of its own. Streams are grouped by the information they carry, among them FUT-INFO and OPT-INFO for instruments, the order book depth streams, the trades streams, ORDERS-LOG and NEWS, each with incremental, snapshot or replay channels.

A single Udp packet may hold several Fast messages, but the system currently sends one per packet and keeps each within the 1500 byte Ethernet MTU. The four byte preamble repeats Msg Seq Num so a recipient can arbitrate Feeds A and B and find gaps without decoding the Fast message.

In the snapshot and replay channels a Sequence Reset message marks the start of each new snapshot cycle.

### Transport

Udp multicast, every stream sent twice as Feeds A and B on separate groups, each Fast message preceded by a four byte little endian preamble holding its sequence number. Tcp recovery of a range of missed messages requested with a Market Data Request, each message prefixed by its length in four little endian bytes.

### Key Characteristics

- **Fast 1.1** - Fix messages encoded to the Fast 1.1 specification against published Xml templates
- **Sequence number preamble** - Four little endian bytes before every message repeat its Msg Seq Num
- **Feeds A and B** - Every stream is broadcast twice on separate groups for arbitration
- **Incremental and snapshot** - Incremental streams with snapshot and replay channels for recovery
- **Legacy feed** - Being superseded on Spectra by the SIMBA binary market data

