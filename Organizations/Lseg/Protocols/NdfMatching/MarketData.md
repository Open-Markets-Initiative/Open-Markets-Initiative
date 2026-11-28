## NdfMatching Market Data: Market Data

Unscreened conflated order book, security status, statistics and security definitions for LSEG NDF Matching instruments in big endian Simple Binary Encoding framed by the Simple Open Framing Header.

### Overview

Every session and application message is a component with its own Simple Open Framing Header and Sbe header; a Premium Feed network payload may carry several components, such as a Context followed by an Encrypted Wrap or a Security Status.

The Premium Feed conflates updates over a 50 millisecond interval and marks the end of each interval with an End of Conflation message on its own channel.

### Transport

Premium Market Data Feed: Udp multicast for collocated subscribers on end of conflation, security definition, Sef and Rmo market data channels; snapshot and incremental messages travel inside an Encrypted Wrap, sequenced by Fixp Topic and Context messages. Standard Market Data Feed: Tls encrypted Tcp to each market data Shard, with a Fixp Negotiate and Establish session and subscription requests.

### Key Characteristics

- **Conflated market by price** - Price level book changes published per conflation interval
- **Unscreened prices** - All participants trade via central counterparties, so every subscriber receives the same unscreened feed
- **Machine-readable schema** - The wire layout is published as an Sbe message schema

