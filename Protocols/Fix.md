## FIX: Financial Information eXchange

Industry standard electronic messaging protocol for real-time exchange of securities transaction information, developed and maintained by the FIX Trading Community.

### Overview

FIX is the most widely adopted electronic communication protocol for securities trading worldwide. Originally authored in 1992 by Robert Lamoureux and Chris Morstatt to enable equity trading data exchange between Fidelity Investments and Salomon Brothers, FIX has grown into the de facto messaging standard for pre-trade and trade communication across global financial markets.

The protocol supports the full trade lifecycle from indications of interest and order routing through execution reporting, allocations, and confirmations. FIX is used across equities, fixed income, foreign exchange, derivatives, and other asset classes. It is governed by the FIX Trading Community, a non-profit industry standards body whose members include major financial institutions, exchanges, and technology vendors.

The FIX standard has evolved through multiple versions, from FIX 4.0 through FIX 5.0 SP2. FIX 5.0 introduced the FIXT transport independence framework, separating the session layer from the application layer to allow independent versioning and alternative transports. FIX also supports encoding in FAST (FIX Adapted for Streaming), FIXML (XML-based), SBE (Simple Binary Encoding), and GPB (Google Protocol Buffers).

### Transport

FIX traditionally operates over TCP using the tag=value text encoding format. The session layer handles connection management, message sequencing, heartbeats, and gap recovery. With FIXT 1.1 in FIX 5.0, the session and application layers were formally separated, enabling the session layer to carry messages from different application versions and supporting alternative transports.

### Key Characteristics

- **Tag=value format** - Messages composed of tag=value pairs separated by SOH delimiters providing human-readable extensible encoding
- **Session layer** - Built-in session management with logon, logout, heartbeat, sequence number tracking, and resend requests
- **Bidirectional** - Supports full two-way communication between counterparties
- **Extensible** - User-defined fields and custom message types allow venue-specific extensions
- **Version negotiation** - FIXT session layer supports application message versioning
- **Vendor neutral** - Open standard not tied to any specific technology provider
