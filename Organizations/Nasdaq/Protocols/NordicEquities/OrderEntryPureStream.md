## NordicEquities Order Entry Pure Stream: Nasdaq Nordic Order Entry Protocol, PureStream Variant

Order entry protocol for the Nasdaq Nordic equities markets running on the Inet Nordic platform.

### Overview

Ouch 5 is the native order entry protocol for the Nasdaq Nordic cash equity markets. Clients enter, replace and cancel orders over a SoupBin Tcp session, and the exchange acknowledges each request and reports the full lifecycle of the order through accepted, replaced, cancelled, executed, broken and restated messages.

Orders carry the MiFid II short codes for client, investment decision maker and execution decision maker, qualified by a packed party role bitfield. Several messages end with an optional appendage, a run of tag value elements that carries the remaining order attributes.

### Transport

Tcp session framed by SoupBin Tcp, with client requests carried in unsequenced data packets and exchange responses in sequenced data packets.

### Key Characteristics

- **Order entry** - Enter, replace and cancel orders with full lifecycle reporting
- **Bidirectional** - Client requests unsequenced, exchange responses sequenced
- **Tag value appendage** - Optional trailing attributes carried as tag value elements
- **SoupBin Tcp** - Sequenced Tcp session with login and recovery

