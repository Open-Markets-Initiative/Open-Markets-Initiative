## Lse Mifid: MiFID II Post Trade

MiFID II post trade transparency service publishing regulatory trade reports for London Stock Exchange instruments over the Group Ticker Plant.

### Overview

MiFID II Post Trade is the Lseg Group Ticker Plant regulatory transparency service for London Stock Exchange. The MiFID II Trade message reports each publishable transaction with the identifiers, flags and indicators required by MiFID II post trade transparency, including the transaction identification code, venue of execution and publication date and time.

Price and quantity on this service are expressed as Ascii MiFID Decimal strings and timestamps as Iso 8601 date and time strings, so the values published match the regulatory representation rather than the scaled binary encoding used on the order book service lines.

### Transport

Udp multicast using the Lseg Group Ticker Plant unit header framing for real time delivery of sequenced binary messages. Tcp for the Group Ticker Plant replay and recovery services used to recover missed multicast messages.

### Key Characteristics

- **Regulatory reporting** - Trade reports carry the full MiFID II post trade transparency field set
- **Decimal encoding** - Price and quantity are carried as Ascii MiFID Decimal strings rather than scaled integers
- **Iso 8601 timestamps** - Trading and publication times are reported as Ascii date and time strings
- **Flag indicators** - Modification, deferral, algorithmic and price formation indicators accompany each report

