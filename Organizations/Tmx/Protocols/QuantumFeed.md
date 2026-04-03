## QuantumFeed: Tmx QuantumFeed Market Data

Tmx Group's market data platform providing Level 1 and Level 2 feeds for Tsx, Tsxv, and Tsx Alpha Exchange equities via Udp multicast.

### Overview

QuantumFeed is the Tmx Group's market data delivery platform for real-time distribution of equity market information. It provides multiple feed levels including Level 1 (top of book with best bid/offer and last sale) and Level 2 (full depth of book with order-by-order visibility) for Tsx, Tsxv, and Tsx Alpha Exchange-listed securities.

The platform delivers data through dedicated feed services per exchange and level. Tsx and Tsxv Level 1 and Level 2 feeds each have separate business message specifications, as does the Alpha Exchange Level 1 and Level 2 feeds. QuantumFeed includes a service access guide defining connectivity requirements and an order book guide describing how to construct and maintain the book from the message stream.

### Transport

Udp multicast with a proprietary session access protocol. The service access guide defines multicast group assignments, connectivity architecture, and gap recovery procedures.

### Key Characteristics

- **Multi-level feeds** - Level 1 top of book and Level 2 full depth of book
- **Multi-exchange** - Tsx, Tsxv, and Tsx Alpha Exchange feeds
- **Binary encoding** - Compact binary message format for low-latency delivery
- **Udp multicast** - Real-time distribution via multicast groups
- **Order book construction** - Detailed order book guide for book state management
- **Sequenced messages** - Sequence numbers for gap detection
