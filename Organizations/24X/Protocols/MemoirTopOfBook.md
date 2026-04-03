## Memoir Top Of Book: 24X Best Bid And Offer Data

Sbe-encoded market data protocol providing top of book best bid and offer information for securities traded on the 24X National Securities Exchange.

### Overview

Memoir Top Of Book is the best bid and offer market data protocol for 24X, delivering real-time Bbo updates for all listed instruments. Built on the Memx technology platform, the protocol uses Simple Binary Encoding (Sbe) for efficient binary message encoding.

The feed provides a lightweight, bandwidth-efficient view of the best available prices on each side of the book. Memoir Top Of Book is designed for subscribers who require current best bid and offer without full depth of book detail.

### Transport

Udp multicast. Bbo updates are disseminated in real time on multicast groups with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Sbe encoded** - Fixed-length binary fields for efficient low-latency parsing
- **Memx platform** - Built on proven Memx exchange technology
- **Best bid and offer** - Top of book pricing for each instrument
- **Bandwidth efficient** - Lightweight alternative to full depth feed
- **Sequence numbered** - Packets carry sequence numbers for gap detection
