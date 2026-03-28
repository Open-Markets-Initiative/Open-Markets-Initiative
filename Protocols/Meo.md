## MEO: MIAX Express Orders

MIAX's proprietary binary order entry protocol designed for ultra-low-latency order submission and management on MIAX Pearl Equities and other MIAX exchange platforms.

### Overview

MIAX Express Orders (MEO) is a feature-rich binary order interface that provides exceptional determinism, throughput, and ultra-low latency to the MIAX trading engines. MEO messaging uses binary numeric fields, fixed-length ASCII fields, and variable-length bulk messages to utilize bandwidth efficiently. The MIAX Pearl Equities assigned Symbol ID of each security is sent in every order message, allowing firms to tie each message to a security symbol without additional lookups.

MEO is a synchronous messaging interface that supports an N-in-flight paradigm to the matching engines. Upon receipt of N binary orders, MEO will not read the firm-facing order entry ports until it sends out a response, providing deterministic behavior for latency-sensitive trading strategies. Each MEO interface acts as a gateway to all matching engines and routes order messages to the appropriate engine based on the security.

Each MEO interface provides one Full Service Port (FSP) and one Priority Purge Port. The Full Service Port supports all MEO order input message types, while the Priority Purge Port provides a dedicated low-latency path for mass cancel operations. MEO supports Cancel-Replacement orders and bulk order messages that carry many orders in a single transmission.

### Transport

MEO operates over TCP using MIAX's proprietary SesM (TCP Session Management) protocol for options exchanges and ESesM (Extended TCP Session Management) for equities. SesM/ESesM is a lightweight point-to-point protocol providing session management including authentication, sequencing, heartbeats, and gap fills. Bidirectional heartbeats enable quick detection of link failures.

### Key Characteristics

- **Binary encoding** - Fixed-length binary numeric fields and ASCII fields for minimal bandwidth usage
- **Ultra-low latency** - Architecture optimized for deterministic low-latency order processing
- **N-in-flight model** - Synchronous paradigm where the exchange throttles intake after N outstanding messages
- **Dual port design** - Full Service Port for all order types and Priority Purge Port for mass cancel operations
- **Bulk messaging** - Single message can carry multiple Auto-Replace or Standard orders
- **Symbol ID mapping** - Orders reference securities by numeric Symbol ID rather than text symbols
- **SesM/ESesM session layer** - Proprietary TCP session management with authentication, sequencing, and gap recovery
