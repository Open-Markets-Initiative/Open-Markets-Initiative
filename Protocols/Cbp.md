## Cbp: Currenex Binary Protocol

Proprietary binary protocol suite developed by Currenex, a State Street subsidiary, for low-latency foreign exchange trading including electronic streaming prices, order entry, and market data.

### Overview

The Currenex Binary Protocol encompasses a family of binary protocols used on the Currenex electronic FX trading platform. Currenex provides institutional-grade foreign exchange trading services, connecting market participants to over 60 streaming banks, non-banks, and an anonymous ECN (FXTrades) with a consolidated Central Limit Order Book.

The protocol suite is adapted from Nasdaq's ITCH and OUCH binary protocols for the foreign exchange market. Currenex ITCH delivers executable streaming prices (ESP) from Market Makers to Market Participants for FX Spot and Precious Metals Spot. Currenex OUCH provides a low-latency binary order entry interface for submitting, modifying, and cancelling orders.

Currenex offers both Maker and Taker APIs through the OUCH protocol. The Maker API is designed for liquidity providers streaming prices, while the Taker API is designed for participants consuming liquidity. The platform supports multiple execution methods including ESP, Request for Stream (RFS), and Request for Quote (RFQ).

### Transport

Currenex ITCH is supported over both TCP and UDP with minimal differences between the two transports. Currenex OUCH operates exclusively over TCP for reliable order delivery. Both protocols use binary encoding with big-endian (network byte order) representation for all integer fields. The session layer includes heartbeat monitoring with 3-second intervals requiring immediate response.

### Key Characteristics

- **Binary encoding** - Signed big-endian binary encoded fields in network byte order
- **Dual transport** - ITCH supports both TCP and UDP; OUCH operates over TCP
- **Heartbeat monitoring** - 3-second heartbeat interval with mandatory immediate response
- **FX-optimized** - Adapted from Nasdaq equity protocols for foreign exchange workflows
- **ESP delivery** - Real-time executable streaming prices from multiple liquidity providers
- **High precision** - 64-bit signed long amounts for precise FX price representation
- **Maker/Taker APIs** - Separate interfaces for liquidity providers and consumers

