## SEED: Stock Exchange Electronic Delivery

High-performance binary order entry protocol developed by the Texas Stock Exchange (TXSE) for low-latency access to US equity markets.

### Overview

SEED is the native binary order entry protocol for the Texas Stock Exchange (TXSE), engineered to provide market participants with high-performance, low-latency order submission, modification, and cancellation capabilities. TXSE designed SEED as a purpose-built binary protocol optimized for the demands of modern electronic equity trading, offering an alternative to FIX for participants requiring the lowest possible latency.

SEED is part of a broader protocol suite at TXSE. The exchange also provides FEED, a real-time market data protocol, and RAKE, a payload-agnostic message framing and network session protocol that operates as the transport layer for both SEED and FEED. RAKE follows the OSI network layer model and provides session management, message framing, and sequencing services in both TCP and UDP variants. TXSE also supports FIX 5.0 for standard connectivity.

TXSE was approved by the SEC as a national securities exchange on September 30, 2025, backed by more than $250 million in capital. TXSE plans to launch trading between July 2 and July 17, 2026, with listings expected in the second half of 2026. TXSE provides PCAP files and Wireshark Lua plugins for protocol analysis and testing.

### Transport

SEED order entry messages are transported over RAKE TCP for reliable in-order delivery. Market data via FEED is delivered over RAKE UDP for multicast distribution. RAKE is payload-agnostic, providing a consistent framing and session layer regardless of whether the payload is SEED order entry, FEED market data, or administrative messages.

### Key Characteristics

- **Binary encoding** - Purpose-built binary protocol for minimal serialization overhead and low-latency parsing
- **RAKE session layer** - Payload-agnostic message framing protocol providing session management for both TCP and UDP
- **Dual transport modes** - RAKE TCP for reliable order entry and RAKE UDP for market data dissemination
- **FIX 5.0 alternative** - TXSE also supports FIX 5.0 for participants preferring standard protocol connectivity
- **Testing tools** - PCAP files and Wireshark Lua plugins provided for protocol validation and certification
- **Modern architecture** - Clean-slate exchange design without legacy protocol constraints
