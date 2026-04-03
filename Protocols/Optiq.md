## Optiq: Euronext Optiq Trading Platform

Multi-asset trading platform developed by Euronext providing SBE-encoded binary protocols for order entry and market data dissemination across all Euronext exchanges, replacing the legacy Universal Trading Platform (UTP).

### Overview

Optiq is Euronext's proprietary trading platform, introduced to replace the aging Universal Trading Platform across all Euronext markets. The migration consolidated Euronext's cash and derivatives markets onto a single modern technology stack designed for lower latency, higher throughput, and improved resilience. Optiq serves as the foundation for both order entry and market data distribution across Euronext Paris, Amsterdam, Brussels, Lisbon, Dublin, Oslo, and Milan (Borsa Italiana).

The platform is organized around two primary gateways: the Order Entry Gateway (OEG) for submitting and managing orders, and the Market Data Gateway (MDG) for receiving real-time and snapshot market data. The OEG supports two encoding interfaces: a FIX 5.0 SP2 text-based protocol for broader compatibility, and a Simple Binary Encoding (SBE) binary protocol optimized for low-latency trading. The MDG exclusively uses SBE encoding over UDP multicast. MDG Lite provides a compressed variant using LZ4 block-mode compression to minimize bandwidth.

SBE was designed within the FIX Protocol Limited organization as a fixed-position, fixed-field-length encoding that supports direct access to data fields without sequential parsing. Binary data uses little-endian byte ordering, and alphanumeric fields are encoded in UTF-8. Open-source SBE tools from Real Logic can be used to generate encoders and decoders from the Euronext-maintained XML template files.

### Transport

The Order Entry Gateway operates over TCP with persistent connections, authentication, and heartbeat-based session management. The Market Data Gateway distributes data via UDP multicast, with each segment assigned dedicated multicast groups for real-time incremental data and snapshot recovery. MDG Lite uses LZ4 compression on multicast channels for reduced bandwidth.

### Key Characteristics

- **SBE binary encoding** - Fixed-position, fixed-length fields using Simple Binary Encoding for minimal decode latency
- **Dual gateway architecture** - Separate Order Entry Gateway (OEG) and Market Data Gateway (MDG)
- **FIX 5.0 SP2 compatibility** - OEG supports both SBE binary and FIX 5.0 text interfaces for order entry
- **UDP multicast market data** - MDG delivers real-time and snapshot feeds over multicast with SBE encoding
- **LZ4 compression** - MDG Lite provides compressed multicast channels for reduced bandwidth consumption
- **Little-endian byte order** - All binary data encoded in Intel byte order with UTF-8 text fields
- **Multi-market coverage** - Single platform spanning seven Euronext exchanges for cash and derivatives
- **Template-driven** - SBE XML templates define message schemas enabling code generation
