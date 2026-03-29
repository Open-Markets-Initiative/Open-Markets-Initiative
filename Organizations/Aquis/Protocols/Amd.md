## Amd: Aquis Market Data

Binary market data protocol for disseminating real-time pricing and order book data on the Aquis Exchange.

### Overview

Amd is the native market data protocol for Aquis Exchange, delivering real-time order book and trade data for equities traded across Aquis European venues. The protocol provides a binary-encoded market data feed optimized for low-latency consumption by trading firms and market data vendors.

Amd delivers incremental order book updates, trade reports, instrument status changes, and reference data. The feed supports full depth of book visibility with granular add, modify, and delete messages enabling subscribers to maintain an accurate real-time view of order book state.

### Transport

Udp multicast. Market data is disseminated on multicast groups with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Binary encoded** - Efficient binary message format for low-latency processing
- **Full depth of book** - Order book updates at every price level
- **Incremental updates** - Real-time add, modify, and delete messages for book maintenance
- **Trade reporting** - Last sale and trade condition data
- **Instrument status** - Trading phase and halt notifications
- **Sequence numbered** - Packets carry sequence numbers for gap detection
