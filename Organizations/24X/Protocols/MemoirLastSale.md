## Memoir Last Sale: 24X Trade Data

Sbe-encoded market data protocol providing last sale trade information for securities traded on the 24X National Securities Exchange.

### Overview

Memoir Last Sale is the trade reporting market data protocol for 24X, delivering real-time trade execution data including price, quantity, and trade condition indicators. Built on the Memx technology platform, the protocol uses Simple Binary Encoding (Sbe) for efficient binary message encoding.

The feed disseminates trade messages as executions occur, providing subscribers with timely last sale information for all listed instruments. Trade messages include relevant condition codes and indicators for regulatory reporting and downstream processing.

### Transport

Udp multicast. Trade messages are disseminated in real time on multicast groups with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Sbe encoded** - Fixed-length binary fields for efficient low-latency parsing
- **Memx platform** - Built on proven Memx exchange technology
- **Real-time trades** - Trade executions disseminated as they occur
- **Trade conditions** - Condition codes and indicators included with each trade
- **Sequence numbered** - Packets carry sequence numbers for gap detection
