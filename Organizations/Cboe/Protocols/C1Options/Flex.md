## Cboe Options Flex

Pitch feed providing market data for flexible options instruments traded on Cboe Options Exchange.

### Overview

Options Flex delivers real-time market data for flexible options contracts on Cboe Options Exchange. Flex options allow customized strike prices, expiration dates, exercise styles, and settlement terms beyond the standard listed options series, and this feed provides order and execution data for those instruments.

The feed includes instrument definition messages for newly created flex series along with ongoing order activity and trade reports.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Flexible terms** - Market data for options with customized strikes, expirations, and settlement
- **Instrument definitions** - Notifications when new flex series are created
- **Order and trade data** - Real-time activity for flex options instruments
