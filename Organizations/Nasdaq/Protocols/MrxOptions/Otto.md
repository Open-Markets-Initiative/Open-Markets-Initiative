## MrxOptions Otto: Nasdaq MRX Ouch to Trade Options (OTTO)

Ouch-based binary order entry protocol for simple, complex and cross orders, auctions and auction responses, complex instrument creation, mass cancel and post trade modification on Nasdaq MRX.

### Overview

OTTO is modeled on the semantics of Nasdaq binary Ouch and extended for options trading. One message set manages orders for simple and complex (including stock combination) instruments, with short forms of New Order and Order Accepted to minimize bandwidth. Instruments are identified by the single numeric InstrumentId published in the simple and complex instrument directory notifications.

Version 3.0.0 adds Flex options support: an Auction Duration and Flex Auction type, repeating Flex leg blocks on New Order (Long Form), New Cross Order, Order Accepted (Long Form) and Auction Notification, an eight character Security Symbol in the simple directory and version fields on the System Event. The extended trading hours edition adds Session Eligibility for MRX.

### Transport

Tcp via SoupBinTcp (Soup 3) for authenticated sessions; requests travel in client unsequenced data packets and every notification from the OTTO host is a sequenced data packet.

### Key Characteristics

- **Nasdaq Ouch family** - Fixed width big endian binary messages modeled on Ouch
- **SoupBinTcp framed** - Session login, heartbeat and sequenced recovery
- **Simple and complex orders** - Single message set for options, standard and stock combinations
- **Auctions** - Block, exposure, flex, facilitation, PIM and solicitation auctions and responses
- **Post trade** - Trade details and modify trade clearing reassignment

