## Cboe Options Csmi Index

Csm index feed providing real-time streaming index values for Cboe-calculated indices.

### Overview

Options Csmi Index delivers real-time calculated index values for indices disseminated by Cboe using the Csm protocol. The feed provides continuously updated index levels as underlying component prices change, serving participants who require low-latency index value data.

The feed covers Cboe-proprietary indices and other indices calculated and disseminated through Cboe's index infrastructure. Index values are published at regular intervals and on component price changes throughout the trading session.

### Transport

Udp multicast delivery with recovery mechanisms for gap handling.

### Key Characteristics

- **Streaming index values** - Real-time calculated index levels
- **Csm protocol** - Delivered using the Csm message encoding framework
- **Continuous updates** - Index values refreshed as component prices change
- **Cboe index coverage** - Proprietary and disseminated index calculations
