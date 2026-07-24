## ChinaConnect SSE: Orion Market Data China Connect SSE

UDP multicast real-time market data for the Northbound Shanghai Stock Exchange (SSE A-Share) channel of the Hkex China Connect programme. Carries Sequence Reset, DR Signal, Market Definition, Security Definition, Security Status, Top Of Book, and Statistics messages. MarketCode within messages is ASHR.

### Overview

SSE is one of the two per-market real-time feeds in the OMD-CC family. Wire format is identical to the SZSE feed; the two are separated only by multicast channel assignment and by the MarketCode field (ASHR for SSE, ASZR for SZSE).

### Transport

Udp multicast delivery on dual A/B channels dedicated to the SSE A-Share market.

