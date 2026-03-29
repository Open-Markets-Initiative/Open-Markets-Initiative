## Esp: Currenex Streaming Prices

Binary market data protocol for streaming executable foreign exchange prices from Currenex using Cbp with Itch-based encoding.

### Overview

Esp (Electronic Streaming Prices) is Currenex's market data protocol for delivering real-time streaming Fx quotes from liquidity providers to consumers. The protocol is built on the Currenex Binary Protocol (Cbp) framework using an Itch-based message encoding, providing binary-efficient delivery of indicative and executable foreign exchange prices across supported currency pairs.

Esp delivers continuous price updates showing bid and offer rates from multiple liquidity providers, enabling consumers to view and interact with live Fx pricing. The feed includes price depth, provider identification, and rate validity information. The Itch-based encoding provides a compact binary format familiar to participants already consuming Itch-family market data from other venues.

### Transport

Tcp connections to Currenex Esp gateways. Sessions are established with authentication and maintained through heartbeat exchanges. Message sequencing supports reliable delivery and gap detection.

### Key Characteristics

- **Cbp/Itch-based encoding** - Binary message format built on Currenex Binary Protocol with Itch conventions
- **Streaming Fx prices** - Continuous executable bid and offer rates for currency pairs
- **Multi-provider depth** - Quotes from multiple liquidity providers visible to consumers
- **Rate validity** - Price freshness and validity indicators for execution decisions
- **Spot Fx focus** - Primary coverage of spot foreign exchange currency pairs
- **Low-latency delivery** - Binary encoding optimized for minimal processing overhead
