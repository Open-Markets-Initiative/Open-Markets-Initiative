## Omd: HKEX Orion Market Data

Binary market data dissemination platform operated by Hong Kong Exchanges and Clearing (HKEX) providing real-time low-latency market data for securities and derivatives markets via IP multicast.

### Overview

The Orion Market Data (OMD) platform is HKEX's market data infrastructure for distributing real-time price, trade, and order book information to market participants. OMD replaced earlier market data systems with a modern high-throughput architecture designed to handle the data volumes and latency requirements of contemporary electronic trading. The platform uses an efficient binary message format optimized for fast encoding, decoding, and minimal bandwidth consumption.

OMD is divided into two primary feeds based on asset class: OMD-C for the securities (cash) market and OMD-D for the derivatives market. OMD-C covers equities, warrants, callable bull/bear contracts (CBBCs), exchange-traded funds, and other securities listed on the Stock Exchange of Hong Kong (SEHK). OMD-D covers futures and options traded on the Hong Kong Futures Exchange (HKFE). Additionally, OMD-CC provides market data for China Connect securities under the Stock Connect program linking Hong Kong with Shanghai and Shenzhen exchanges.

All OMD feeds publish data using IP multicast over UDP with dual-channel redundancy where every message is duplicated and sent over two separate multicast groups. Binary values use little-endian encoding with support for unsigned and signed integers. A retransmission recovery service operates over TCP unicast, and a dedicated multicast channel carries Disaster Recovery Signal messages for site failover coordination.

### Transport

OMD distributes all market data via UDP multicast. Each data feed is assigned dedicated multicast groups organized by market segment and data type. Messages are duplicated across two independent multicast channels (Line A and Line B). Each channel maintains its own session with strictly increasing sequence numbers for gap detection. A TCP retransmission service allows clients to request specific missed messages. A dedicated DR Signal multicast channel broadcasts failover activation and completion notifications.

### Key Characteristics

- **Binary encoding** - Compact binary message format with little-endian byte order for high throughput and low latency
- **UDP multicast delivery** - One-to-many distribution using IP multicast for efficient bandwidth utilization
- **Dual-channel redundancy** - Every message sent on two independent multicast lines for packet loss mitigation
- **Sequence-numbered messages** - Strictly increasing per-channel sequence numbers for gap detection
- **TCP retransmission** - Unicast recovery service for requesting missed messages by sequence number
- **Disaster recovery signaling** - Dedicated multicast channel for site failover notifications
- **Asset-class separation** - Distinct feeds for securities (OMD-C), derivatives (OMD-D), and China Connect (OMD-CC)
- **Refresh service** - Periodic snapshot publication for initial synchronization and recovery

