## Soup Bin Tcp: Nasdaq Session Authenticated Tcp Transport

Session layer providing authenticated Tcp sessions with sequence number tracking and gap recovery used across Nasdaq binary protocols including Itch, Ouch, and Glimpse.

### Overview

SoupBinTcp is the Nasdaq session layer protocol that provides authenticated Tcp sessions with sequence number tracking, heartbeat monitoring, and gap recovery. It is the session foundation for a family of Nasdaq binary protocols including Itch for market data, Ouch for order entry, and Glimpse for snapshot recovery, as well as many other Itch-style feeds from exchanges licensing the Nasdaq technology.

### Transport

Tcp for persistent authenticated SoupBinTcp sessions carrying login, logout, heartbeat, sequenced data, and unsequenced data messages.

### Key Characteristics

- **Session based** - Authenticated login and logout handshake
- **Sequence tracking** - Ordered delivery with sequence numbers
- **Heartbeat monitoring** - Periodic keepalive exchanges
- **Gap recovery** - Request replay of missed sequence ranges
- **Shared layer** - Used by Itch, Ouch, Glimpse, and other Nasdaq protocols

