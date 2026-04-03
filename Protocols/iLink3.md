## iLink 3: CME Globex Binary Order Entry

Binary order entry protocol developed by CME Group for submitting and managing orders on the CME Globex electronic trading platform, using Simple Binary Encoding over a FIXP session layer.

### Overview

iLink 3 is CME Group's current-generation order entry API for trading futures, options, spreads, BrokerTec fixed income, and EBS FX products on CME Globex. It replaced the FIX tag-value-based iLink 2 protocol with a modern binary encoding based on Simple Binary Encoding (SBE), providing significantly lower encoding and decoding latency. The protocol went fully live on July 26, 2020, across CME, CBOT, NYMEX, and COMEX exchanges.

iLink 3 is structured as two distinct layers: a lightweight point-to-point session layer based on the FIX Performance Session Protocol (FIXP), and a business layer carrying order entry and execution messages in SBE format. The FIXP session layer handles connection management, sequencing, and keepalive negotiation without embedding administrative information in business messages, resulting in leaner order messages with standard sizes, fixed positions, and fixed-length fields.

The protocol supports Cancel On Conclusion (COC) as a mandatory safety feature, which automatically cancels all working orders when a session terminates gracefully. Session establishment involves a Negotiate and Establish handshake with UUID assignment.

### Transport

iLink 3 operates over TCP for reliable ordered message delivery between client systems and CME Globex matching engine gateways. The FIXP session layer provides negotiation, establishment with sequence number synchronization, bidirectional sequencing for message ordering and gap detection, keepalive heartbeats for connection liveness monitoring, and graceful termination with Cancel On Conclusion.

### Key Characteristics

- **SBE encoded** - Simple Binary Encoding for ultra-low latency encoding and decoding
- **FIXP session layer** - Lightweight FIX Performance protocol with no session-level headers on business messages
- **Fixed message sizes** - Standard message layouts with fixed positions and fixed-length fields
- **Cancel On Conclusion** - Mandatory auto-cancellation of all working orders on session disconnect
- **Mass quoting** - Efficient bulk quoting for market makers
- **Self-match prevention** - Built-in controls to prevent self-trading
- **Schema versioned** - XML-based SBE templates published on CME SFTP servers
