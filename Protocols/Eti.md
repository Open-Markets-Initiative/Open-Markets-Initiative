## ETI: Enhanced Trading Interface

High-performance binary order entry protocol developed by Deutsche Borse for the T7 trading platform, supporting order management, quote entry, and trade management for both derivatives and cash markets.

### Overview

The Enhanced Trading Interface (ETI) is the native trading interface of the T7 trading system operated by Deutsche Borse Group. It provides direct, low-latency access for submitting and managing orders, quotes, and related trading operations. ETI is an asynchronous, message-based protocol that uses FIX 5.0 SP2 application-level semantics with a proprietary session layer and flat binary encoding for maximum performance.

ETI is designed for participants who require the highest throughput and lowest latency for order entry, including high-frequency trading firms, market makers, and algorithmic trading operations. The interface supports multiple session types with different throughput limits: high frequency (HF) sessions for latency-sensitive strategies, low frequency (LF) sessions for regular trading, and LF sessions for back-office operations. Each session type has a configurable throttle that limits the number of requests allowed within a sliding time window.

The protocol supports a wide range of trading workflows including simple and complex order entry, mass quoting for market makers, cross requests, and strategy trading on multi-leg instruments. ETI is deployed across all T7-powered venues including Eurex, Xetra, EEX, and partner exchanges in Vienna, Budapest, Prague, Ljubljana, Zagreb, Sofia, and Malta.

### Transport

ETI uses TCP for reliable ordered message delivery between participant systems and the T7 trading gateway. A session is initiated by establishing a TCP connection and completing a logon handshake. Participants may send multiple requests without waiting for individual responses, and the gateway processes them asynchronously. The protocol includes session recovery with automatic retransmission of missed messages after reconnection.

### Key Characteristics

- **Flat binary encoding** - Proprietary binary format with FIX 5.0 SP2 semantics for minimal serialization overhead
- **Asynchronous messaging** - Multiple requests can be in flight simultaneously without blocking
- **Session-based throttling** - Sliding window throttle limits per session type (HF, LF trading, LF back-office)
- **Persistent and lean orders** - Standard orders survive session disconnects; lean orders are non-persistent for lower latency
- **Mass quoting** - Dedicated message types for efficient two-sided quote entry and management
- **Multi-leg support** - Native support for complex instrument order entry and strategy trading
- **Session recovery** - Automatic retransmission of missed messages after reconnection
- **Self-match prevention** - Built-in functionality to prevent a participant from trading against their own orders
