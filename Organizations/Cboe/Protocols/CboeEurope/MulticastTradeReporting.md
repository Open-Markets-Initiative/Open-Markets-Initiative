## CboeEurope Multicast Trade Reporting: Cboe Europe Trade Reporting Facility

Trade Reporting Facility (TRF) Multicast PITCH trade feeds publishing OTC and SI trades reported to the Cboe Europe TRF as Trade - Extended messages. Part of the Cboe Titanium Europe Multicast PITCH specification and its wire message format.

### Overview

Trade Reporting Facility (TRF) Multicast PITCH trade feeds publishing OTC and SI trades reported to the Cboe Europe TRF as Trade - Extended messages, as section 1.7 of the Cboe Titanium Europe Multicast PITCH specification describes.

### Transport

Udp multicast via the Cboe Pitch Sequenced Unit Header for real-time delivery of sequenced binary market data with A and B feed redundancy. Tcp for the Cboe Europe Gap Request Proxy / spin server used to recover messages missed on the multicast feed.

### Key Characteristics

- **Cboe Pitch** - Native Cboe binary message format, shared with the BXE, CXE and DXE books
- **Multicast delivery** - Udp multicast with gap request proxy recovery

