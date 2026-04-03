## Order Data Feed: SmallX Market Data

Sbe-encoded order data feed providing real-time order and trade information for the SmallX exchange.

### Overview

The SmallX Order Data Feed is a market data protocol using Simple Binary Encoding (Sbe) to disseminate real-time order activity and trade executions on the SmallX exchange. The protocol delivers order book updates including new orders, modifications, cancellations, and trade executions, enabling subscribers to reconstruct the current state of the order book.

The feed uses Sbe encoding with fixed-position, fixed-length fields for efficient parsing and low-latency processing. Messages carry order-level detail providing visibility into individual order events as they occur on the SmallX matching engine, supporting both market surveillance and trading applications.

### Transport

Udp multicast with sequenced packets for efficient delivery of order data to subscribers.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Order-level data** - Individual order events including adds, modifies, and deletes
- **Trade executions** - Real-time execution reports with price and size
- **Multicast delivery** - Udp multicast for efficient one-to-many distribution
- **Sequence numbered** - Packets carry sequence numbers for gap detection
- **Schema versioned** - Sbe Xml templates define message layouts
