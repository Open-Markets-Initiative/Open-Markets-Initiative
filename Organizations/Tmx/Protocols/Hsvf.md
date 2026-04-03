## Hsvf: High Speed Vendor Feed

Proprietary binary protocol with text elements developed by Tmx Group for derivatives market data dissemination on the Montreal Exchange (Mx) Sola trading platform.

### Overview

Hsvf (High Speed Vendor Feed) is the market data protocol for the Montreal Exchange, delivering real-time options and futures quotes, trades, and reference data from the Sola matching engine. The protocol is available in multicast delivery mode for broad real-time distribution to market participants.

Hsvf delivers instrument definitions, best bid and offer updates, last sale trade reports, market state indicators, and end-of-day settlement summaries for all Mx-listed derivatives. The protocol uses a hybrid encoding combining binary framing with text-based field representation, designed for the specific requirements of the Canadian derivatives market.

### Transport

Udp multicast from the Sola platform. The Mx Multicast Feed Service provides connectivity and access management for Hsvf subscribers.

### Key Characteristics

- **Derivatives focused** - Purpose-built for Mx options and futures market data
- **Hybrid encoding** - Combines binary framing with text-based field representation
- **Multicast delivery** - Real-time distribution via Udp multicast
- **Sola platform** - Native market data feed from the Sola matching engine
- **Session-based** - Session management for connection lifecycle
