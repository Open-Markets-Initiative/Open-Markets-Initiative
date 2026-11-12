## NtxOptions Otto: Nasdaq BX Ouch to Trade Options (OTTO)

Ouch-based binary order entry protocol for simple, complex and cross orders, auctions and auction responses, complex instrument creation, mass cancel and post trade modification on the Nasdaq BX options market, now Nasdaq Texas Options.

### Overview

OTTO is modeled on the semantics of Nasdaq binary Ouch and extended for options trading. One message set manages orders for simple and complex (including stock combination) instruments, with short forms of New Order and Order Accepted to minimize bandwidth. Instruments are identified by the single numeric InstrumentId published in the simple and complex instrument directory notifications.

BX came to OTTO at version 2.2, the one edition of the protocol that names it, with support for Block and PRISM auctions and Market Wide Risk Protections. Version 2.2 is otherwise the version 2.1.4 message set, published the same day for the other four markets.

### Transport

Tcp via SoupBinTcp (Soup 3) for authenticated sessions; requests travel in client unsequenced data packets and every notification from the OTTO host is a sequenced data packet.

### Key Characteristics

- **Nasdaq Ouch family** - Fixed width big endian binary messages modeled on Ouch
- **SoupBinTcp framed** - Session login, heartbeat and sequenced recovery
- **Simple and complex orders** - Single message set for options, standard and stock combinations
- **Auctions** - Block and PRISM auctions and responses
- **Post trade** - Trade details and modify trade clearing reassignment

