## OPRA: Options Price Reporting Authority

The Options Price Reporting Authority is the exclusive Securities Information Processor that consolidates and disseminates real-time last sale reports, quotes, and market data for all US equity options exchanges, operated by SIAC and handling some of the highest message rates of any market data feed in the world.

### Overview

OPRA was established to provide a consolidated view of the US listed options market, ensuring all market participants have equal access to real-time options pricing information. Every US equity options exchange is required to report its quotes and trades to OPRA, which validates, consolidates, and redistributes the data. The OPRA Plan is governed by a committee of representatives from all participating options exchanges, with SIAC serving as the technical processor.

The protocol uses two primary interface specifications: the OBI (OPRA Binary Input) format defining how exchanges submit data, and the ODI (OPRA Binary Data Recipient Interface) format defining how consolidated data is distributed to subscribers. Both specifications are based on the NYSE Pillar wire protocol architecture.

OPRA is distinguished by extraordinarily high message volumes driven by the combinatorial explosion of options series across thousands of underlying securities, multiple strike prices, and expiration dates. Peak message rates have exceeded 150 billion messages in a single trading day, with microburst rates reaching tens of millions of messages per second. The 2024 expansion from 48 to 96 multicast lines increased capacity from 400 billion to 1 trillion transactions per day and reduced 99th percentile latency from 543 microseconds to 57 microseconds.

### Transport

OPRA data is disseminated via IP multicast across 96 multicast lines, with each line carrying a subset of options series distributed by underlying symbol. The distribution network operates on a dual-feed architecture with two redundant copies (Side A and Side B) for arbitration. Data is transmitted as variable-length binary blocks with a maximum block size of 1,000 bytes. TCP-based retransmission services are available for gap recovery. Subscribers need in excess of 40 Gbps per side to handle peak aggregate bandwidth, which regularly exceeds 70 Gbps across both copies.

### Key Characteristics

- **Exclusive consolidated options feed** - Single authoritative source for all US equity options market data
- **Extreme message volumes** - Peak daily volumes exceeding 150 billion messages with microburst rates of tens of millions per second
- **96 multicast lines** - Data distributed across 96 channels for load balancing
- **Dual-feed redundancy** - Side A and Side B multicast copies for reliability and gap detection
- **Binary encoding** - Variable-length messages in blocks up to 1,000 bytes based on NYSE Pillar wire protocol
- **OBI/ODI specifications** - Separate binary interface specifications for input and output
- **High bandwidth requirements** - Aggregate bandwidth exceeding 70 Gbps during peak periods
