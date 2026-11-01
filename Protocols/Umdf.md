## Umdf: B3 Fix/Fast Multicast Market Data

Fast-encoded multicast market data protocol publishing order book, trade, instrument definition and reference data for equities and derivatives traded on B3, in market by order, market by price and top of book form.

UMDF FIX/FAST is B3's Fix Adapted for Streaming market data feed covering equities, derivatives, and fixed income on the B3 Puma Trading System, the feed Binary UMDF is regenerated from.

### Overview

UMDF FIX/FAST is the original encoding of B3's Unified Market Data Feed, publishing incremental order book updates, snapshots for recovery, instrument definitions, security status, settlement prices, open interest and news as Fix messages compressed with Fix Adapted for Streaming. B3 continues to publish it, regenerating it from the Binary Sbe feed since 11 March 2024.

Each template file states a dictionary per template rather than one for the feed, so a template's transfer operators carry state only against other messages of that template and no feed wide dictionary reset arises. The MDSequenceReset template is the Fix SequenceReset application message, which announces a new sequence number rather than clearing decoder state.

A datagram is framed outside Fast: every message is preceded by a technical header holding the sequence number, the number of chunks the message was split into, the chunk this datagram carries and the Fast payload's length, all big endian. The payload itself begins with the Fast presence map, so a decoder reads the header with fixed width fields and the message with the template the presence map identifies.

### Transport

Udp multicast carrying one or more messages per datagram, each a ten byte unencoded technical header then a Fast encoded Fix message, a message longer than the datagram split across chunks the receiver reassembles by sequence number. Tcp replay and historical recovery, requested with the same Fast encoded messages the multicast feed publishes.

### Key Characteristics

- **Fast encoded** - Fix Adapted for Streaming 1.1 templates, compressing Fix messages with presence maps and transfer operators
- **Per template dictionaries** - Each template declares its own dictionary, so operator state never crosses message types
- **Technical header** - Ten byte unencoded preamble per message holding sequence number, chunk count, chunk index and payload length
- **Chunked reassembly** - A message larger than one datagram is split across chunks the receiver rejoins by sequence number
- **Multicast delivery** - Real-time Udp multicast on an A and B feed per channel, with Tcp replay for recovery
- **Order book Mbo and Mbp** - Incremental refresh in market by order, market by price and top of book channels
- **Security reference** - Instrument definition and security list messages carried on their own channels
- **Equities and derivatives** - Unified feed across the Bovespa and BM&F segments

