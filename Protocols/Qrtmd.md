## Qrtmd: Quantum Real Time Market Data

Ascii market data encoding used by TMX Group to disseminate Canadian Exchange Group market data, framing each message between Start of Text and End of Text around a twenty two byte ascii header.

### Overview

Quantum Real Time Market Data is the ascii dissemination of the markets TMX Group administers for the Canadian Exchange Group. A service code in the header names the market and tier a feed carries, and every message is a fixed width record whose business content is read by position rather than by tag.

The Level 1 services state their fields as fixed length records, right justified and zero filled when numeric and left justified and blank filled when alphanumeric, with a decimal point implied by the digit pattern the specification states rather than written on the wire. The Level 2 services carry Stamp tag and value content inside the same framing instead.

### Transport

Ip multicast carries the real time feed, one framed message to a packet, the Continuation Indicator in the header providing for a message that exceeds the maximum transmission unit. Tcp carries the recovery channel, on which a client requests a range of sequence numbers and receives the messages framed as the real time feed frames them.

### Key Characteristics

- **Ascii throughout** - Every field is printable ascii, header and business content alike
- **Stx and Etx framed** - Each message sits between Start of Text and End of Text
- **Service coded header** - A three byte service code names the market and tier the feed carries
- **Implied decimals** - Numeric fields state their decimal places by digit pattern, never writing a point
- **Sequenced with recovery** - Every message carries a daily sequence number recoverable over Tcp

