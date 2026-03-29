## Memoir Depth Feed: Boats Full Depth Market Data

Sbe-encoded market data protocol providing full depth of book information for securities traded on Blue Ocean Ats.

### Overview

Memoir Depth Feed is the full depth of book market data protocol for Blue Ocean Ats (Boats), delivering real-time order book updates including every price level across all listed instruments. Built on the Memx technology platform, the protocol uses Simple Binary Encoding (Sbe) for efficient binary message encoding.

The feed provides add, modify, and delete messages for individual orders or price levels, enabling subscribers to maintain a complete view of the order book during overnight trading sessions. Memoir Depth Feed supports both real-time incremental updates and snapshot recovery for initial book construction or gap recovery.

### Transport

Udp multicast. Real-time incremental updates are disseminated on multicast groups with sequence numbers for gap detection. Snapshot feeds are available for periodic full book state recovery.

### Key Characteristics

- **Sbe encoded** - Fixed-length binary fields for efficient low-latency parsing
- **Memx platform** - Built on proven Memx exchange technology
- **Full depth of book** - Every price level visible for complete book reconstruction
- **Incremental updates** - Add, modify, and delete messages for real-time book maintenance
- **Snapshot recovery** - Periodic full book snapshots for gap recovery and initial state
- **Sequence numbered** - Packets carry sequence numbers for gap detection
