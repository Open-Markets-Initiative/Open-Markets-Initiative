## Asts Instrument Definitions: SIMBA ASTS Instrument Definitions

Periodic security definitions of the Moex equities and currency markets, each describing an instrument and its key parameters together with its trading session and trading status. Each packet carries a market data packet header and a single Sbe message.

### Transport

Udp multicast in the snapshot packet format, throttled by a traffic shaper.

### Key Characteristics

- **Security definitions** - Instrument descriptions repeated in cycles
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Rate limited** - Transmission is throttled by a traffic shaper

