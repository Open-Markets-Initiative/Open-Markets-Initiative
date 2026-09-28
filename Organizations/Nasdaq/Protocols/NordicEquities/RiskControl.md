## NordicEquities Risk Control: Nasdaq Nordic Pre-Trade Risk Management Protocol

Binary protocol used by participants to query and configure their Pre-Trade Risk Management account settings, restrictions and limits for the Nasdaq Nordic equities markets running on the Inet Nordic platform.

### Overview

The Pre-Trade Risk Management protocol lets a participant manage the configuration of its logical PRM Account on Inet Nordic. Clients query the next expected user reference number, modify account settings such as block and cancel or fat finger protection, restrict order books and market segments, and set per currency order, trade and open order value limits. The host confirms each change with a response carrying the resulting settings, or rejects it with a reason.

Every message has a fixed length and a single character message type. Optional fields in a modify request are filled with -1 for integers or ascii question marks for alpha fields, which leaves the existing setting unchanged, so sending every field in that form reads back the current configuration. The host also reports port and account rate breaches and publishes the accumulated risk values of an account after order and trade updates.

The specification is marked by Nasdaq as internal use with distribution limited to Nasdaq personnel and authorized third parties subject to confidentiality obligations.

### Transport

Tcp session framed by SoupBin Tcp, with client configuration requests carried in unsequenced data packets and host responses, rate breach alerts and accumulated values in sequenced data packets.

### Key Characteristics

- **Pre-trade risk** - Account settings, restrictions and limits for a PRM Account
- **Bidirectional** - Client requests unsequenced, host responses sequenced
- **Fixed length messages** - Big endian binary numbers and space padded alpha fields
- **Unchanged sentinels** - Optional fields sent as -1 or question marks keep the existing setting
- **SoupBin Tcp** - Sequenced Tcp session with login and recovery

