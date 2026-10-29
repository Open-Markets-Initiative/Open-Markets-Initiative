## Asts Market Data Multicast: Market Data Multicast

The Moscow Exchange Market Data Multicast Fix Fast platform for the Asts markets, publishing statistics, orders, trades, instrument status and instrument definitions as Fix 5.0 Sp2 messages encoded to Fast 1.1, each feed on a multicast group of its own with a Tcp replay service for recovery.

### Overview

The platform sends the tables of the Asts trading system to separate multicast groups: statistics, orders and trades as incremental feeds with snapshot recovery feeds, instrument status, and the instrument definitions feed. The templates tell the equity and bond market from the currency market by template, so a feed of one market is decoded by the templates named for it, FOND for equities and bonds and CURR for currency.

One Fast encoded message never spans more than one Udp packet, and the platform currently sends one message per packet. Every dictionary entry is reset to its initial value after each packet, so operators such as copy and increment act only within a packet, and a packet decodes without the ones before it.

The four byte preamble before each message repeats the message's Msg Seq Num, letting a recipient arbitrate Feeds A and B and detect gaps before decoding the Fast message itself.

### Transport

Udp multicast, each feed on its own multicast address and sent twice as Feeds A and B, every Fast message preceded by a four byte little endian preamble holding its sequence number. Tcp replay of missed messages, each message prefixed by its length in four little endian bytes.

### Key Characteristics

- **Fast 1.1** - Templates published as Xml under the Fast 1.1 template definition schema, without session control protocol
- **Sequence number preamble** - Four little endian bytes before every message repeat its Msg Seq Num
- **One message per packet** - Dictionaries reset after every packet, so each decodes on its own
- **Feeds A and B** - Every feed is sent twice on separate multicast groups for arbitration
- **Market specific templates** - Separate templates for the equity and bond tables and the currency tables

