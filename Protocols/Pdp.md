## Pdp: NYSE Pdp

Legacy binary market data encoding carrying the Nyse Bonds top of book quote feed over Udp multicast, the predecessor of Xdp. The specifications use the acronym Pdp throughout and never expand it.

### Overview

Every Pdp message carries the same sixteen byte common message header, which the specification describes as an envelope and letter paradigm so that subscribers implement line level processing once and then only parse the message bodies they care about. MsgSize counts the header and the body but not its own two bytes, so a message is MsgSize plus two.

Binary fields are Big Endian, which the Quotes specification states twice. This is worth noting because Xdp, the feed family that replaced Pdp, is Little Endian.

Prices are carried as a numerator paired with a PriceScaleCode naming the common power of ten denominator, so a price of 27.56 is a numerator of 2756 with a PriceScaleCode of 2. The header also carries a NumBodyEntries count, so one message can repeat its body several times.

### Transport

Udp multicast, with primary and secondary feeds per multicast group so a packet lost on one can be taken from the other. A Tcp request server answers retransmission, refresh and symbol index mapping requests, and the results are republished on a retransmission multicast group rather than returned inline.

### Key Characteristics

- **Common header** - One sixteen byte envelope precedes every message body
- **Big endian** - Unlike the Xdp family that replaced it
- **Self excluding length** - MsgSize counts the header and body but not its own two bytes
- **Repeating bodies** - NumBodyEntries says how many times the body repeats in one message
- **Dual multicast feeds** - Primary and secondary groups let subscribers recover a dropped packet
- **Scaled prices** - Numerator plus a PriceScaleCode naming the power of ten denominator

