## NtxEquities Last Sale: Nasdaq Texas Last Sale, formerly Nasdaq BX Last Sale (BLS)

Real-time, intra-day trade data feed from the Nasdaq Texas execution system, formerly Nasdaq BX Last Sale.

### Overview

Nasdaq Texas Last Sale, formerly Nasdaq BX Last Sale (BLS), is a direct data feed of real-time, intra-day trade data from the Nasdaq Texas execution system, covering Nasdaq, NYSE and other US exchange listed securities. The current feed is documented in the unified Nasdaq Last Sale Products specification.

The messages are a series of sequenced, variable length binary messages: system events, trade reports, trade cancel/error and trade correction messages, and administrative messages. They are offered over MoldUdp64 and SoupBinTcp.

### Transport

Udp multicast via MoldUdp64, a single broadcast channel with A and B feeds and a rerequest service for missed messages. Tcp via SoupBinTcp for sequenced delivery of the same messages.

### Key Characteristics

- **Last sale** - Trades from the Nasdaq Texas execution system
- **Trade lifecycle** - Trade report, trade cancel/error and trade correction messages
- **Administrative messages** - Stock trading action, Reg SHO, stock directory, MWCB and operational halt messages
- **Nasdaq Itch** - Variable length sequenced binary messages, big endian integers and nanosecond timestamps
- **MoldUdp64 and SoupBinTcp** - MoldUdp64 multicast and SoupBinTcp

