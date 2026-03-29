## iLink 3: Cme Globex Binary Order Entry

Binary order entry protocol for submitting and managing orders on the Cme Globex electronic trading platform using Sbe encoding over a Fixp session layer.

### Overview

iLink 3 is Cme Group's current-generation order entry Api for trading futures, options, spreads, BrokerTec fixed income, and Ebs Fx products on Cme Globex. It replaced the Fix tag-value-based iLink 2 protocol with Simple Binary Encoding (Sbe), providing significantly lower encoding and decoding latency. The protocol went fully live on July 26, 2020, across Cme, Cbot, Nymex, and Comex.

iLink 3 is structured as two layers: a session layer based on the Fix Performance Session Protocol (Fixp) and a business layer carrying order entry and execution messages in Sbe format. The Fixp session layer handles connection management, sequencing, and keepalive without embedding administrative information in business messages. Cancel On Conclusion (Coc) is a mandatory safety feature that automatically cancels all working orders when a session terminates.

### Transport

Tcp to Cme Globex matching engine gateways (Msgw/Cgw). Fixp session layer provides negotiation with Hmac-Sha-256 authentication, establishment with Uuid and sequence number synchronization, bidirectional sequencing, keepalive heartbeats, and graceful termination.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Fixp session layer** - Lightweight session protocol with no headers on business messages
- **Cancel On Conclusion** - Mandatory auto-cancellation of all working orders on disconnect
- **Mass quoting** - Efficient bulk quoting for market makers
- **Self-match prevention** - Built-in controls to prevent self-trading
- **Party details definition** - Persistent trading party and account information
- **Schema versioned** - Xml-based Sbe templates published on Cme Sftp servers
