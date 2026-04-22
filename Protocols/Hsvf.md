## Hsvf: High Speed Vendor Feed

Proprietary binary protocol with text elements developed by TMX Group and licensed to several exchanges for derivatives market data dissemination.

### Overview

HSVF (High Speed Vendor Feed) is a market data protocol designed for the distribution of derivatives trading information, including options and futures quotes, trades, and reference data. Originally developed for the Montreal Exchange (MX), it has been adopted by other TMX Group venues and licensed internationally to exchanges such as BOX Options Exchange.

The protocol delivers real-time best bid and offer updates, last sale trade reports, instrument definitions, and end-of-day settlement summaries. HSVF is available in both multicast and unicast delivery modes depending on the venue and subscriber requirements.

### Transport

HSVF operates over both TCP and UDP, supporting direct data feed delivery to market participants. Multicast delivery is used for broad real-time distribution while unicast provides point-to-point connectivity. The protocol uses a hybrid encoding combining binary framing with text-based field representation.

### Key Characteristics

- **Derivatives focused** - Purpose-built for options and futures market data
- **Hybrid encoding** - Combines binary framing with text-based field representation
- **Real-time delivery** - Designed for low-latency distribution of market data updates
- **Multicast and unicast** - Available in both delivery modes for different connectivity requirements
- **Session-based** - Includes session management for connection lifecycle

