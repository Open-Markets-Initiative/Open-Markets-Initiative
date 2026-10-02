## PsxEquities Last Sale: Nasdaq PSX Last Sale (PLS)

Real-time, intra-day trade data feed from the Nasdaq PSX execution system covering Nasdaq, NYSE and other regional exchange listed securities.

### Overview

Nasdaq PSX Last Sale (PLS) is a direct data feed of real-time, intra-day trade data from the PSX execution system, covering Nasdaq, New York Stock Exchange and other regional exchange listed securities. The current PSX Last Sale is documented in the unified Nasdaq Last Sale Products specification.

The messages are a series of sequenced, variable length binary messages: system events, trade reports, trade cancel/error and trade correction messages, and administrative messages. They are offered over MoldUdp64 and SoupBinTcp.

### Transport

Udp multicast via MoldUdp64, a single broadcast channel with A and B feeds and a rerequest service for missed messages. Tcp via SoupBinTcp for sequenced delivery of the same messages.

### Key Characteristics

- **Last sale** - Trades from the Nasdaq PSX execution system
- **Trade lifecycle** - Trade report, trade cancel/error and trade correction messages
- **Administrative messages** - Stock trading action, Reg SHO, stock directory, MWCB and operational halt messages
- **Nasdaq Itch** - Variable length sequenced binary messages, big endian integers and nanosecond timestamps
- **MoldUdp64 and SoupBinTcp** - MoldUdp64 multicast and SoupBinTcp

