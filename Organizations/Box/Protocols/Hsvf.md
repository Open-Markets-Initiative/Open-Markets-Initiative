## Hsvf: Box High Speed Vendor Feed

Market data protocol for disseminating real-time pricing and order book data on the Box Options Exchange using multicast and unicast delivery on the Sola platform.

### Overview

Hsvf (High Speed Vendor Feed) is the market data protocol used by the Box Options Exchange for real-time dissemination of options pricing, order book, and trade data. The protocol operates on the Sola trading platform and delivers quote, trade, and instrument status information for all listed options series.

Hsvf is available in both multicast and unicast variants, providing flexibility for different subscriber connectivity requirements. The multicast variant delivers data via Udp multicast for high-throughput consumption, while the unicast variant provides a dedicated Tcp stream for subscribers requiring point-to-point delivery. Both variants carry the same market data content including best bid and offer updates, trade reports, and instrument reference data.

### Transport

Udp multicast and Tcp unicast. The multicast variant disseminates data on multicast groups for scalable distribution. The unicast variant provides a dedicated point-to-point Tcp connection. Both carry sequence numbers for message ordering.

### Key Characteristics

- **Sola platform** - Operates on the Sola exchange technology platform
- **Dual delivery modes** - Available in both multicast and unicast variants
- **Options focused** - Quote and trade data for listed options series
- **Real-time quotes** - Best bid and offer updates for all series
- **Trade reporting** - Last sale data with trade condition indicators
- **Sequence numbered** - Messages carry sequence numbers for gap detection
