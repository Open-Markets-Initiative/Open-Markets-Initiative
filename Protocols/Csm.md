## CSM: Cboe Streaming Market

Proprietary market data streaming protocol developed by Cboe Global Markets for real-time dissemination of index values, options top-of-market data, and related market information via IP multicast.

### Overview

Cboe Streaming Market (CSM) is a family of low-latency data feeds operated by Cboe Data Services that provide real-time streaming market data from Cboe exchanges. The CSM feeds were originally introduced by CBOE Holdings through its Market Data Express subsidiary as a direct-access data service, offering subscribers uncompressed top-of-the-order-book details, trade data, and calculated index values.

The most prominent CSM feed is the Cboe Global Indices Feed, formerly known as CSMI (Cboe Streaming Market Indexes). This feed is the definitive real-time streaming data service for major volatility and strategy indices including SPX, VIX, and indices from providers such as Morningstar, S&P Dow Jones, FTSE Russell, and MSCI. Most index values are updated every 15 seconds during trading hours.

As Cboe migrated its options exchanges to the Titanium platform, some CSM feed functions have been supplemented or replaced by the Multicast Pitch and Multicast TOP protocols for options order book data. CSM continues to serve as the primary delivery mechanism for Cboe-calculated index data.

### Transport

CSM transmits data using IP multicast over UDP. Communication is one-way from the exchange to subscribers with no mechanism for retransmission of missed packets. Each multicast packet consists of a packet header followed by one or more messages. The packet header contains the sending timestamp, message count, and first sequence number for gap detection. Messages are encoded using a mix of ASCII characters and binary data, with template-based message structures defined by XML template files.

### Key Characteristics

- **Multicast UDP delivery** - One-way real-time distribution with no retransmission mechanism
- **Mixed ASCII and binary encoding** - Messages use a combination of ASCII characters and binary data fields
- **Template-based messages** - Each message type defined by a unique template ID with XML template specifications
- **Sequenced packets** - Packet headers include sequence numbers for gap detection
- **Index calculation data** - Provides calculated index values including bid, ask, and last-sale-based computations
- **Stable message templates** - Templates do not change during the trading day with advance notice for changes
