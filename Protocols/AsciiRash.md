## AsciiRash: Nasdaq Routing And Special Handling (RASH) message format (fixed length ascii)

Fixed length ascii message format of the Nasdaq RASH (Routing And Special Handling) order entry ports of the Nasdaq Stock Market, BX, Nasdaq Texas and PSX. Inbound messages enter orders with routing, discretion, pegging, reserve and cross instructions and cancel them; outbound messages, each opening with its time stamp and a one character type, report system events, accepted, canceled, rejected and executed orders and broken trades.

### Overview

RASH lets participants enter orders, cancel existing orders and receive executions, with advanced functionality including discretion, random reserve, pegging and routing. Every message type has a fixed length and is composed of non-control ascii bytes.

Numeric fields are digits right justified and zero filled, alpha fields left justified and space filled, prices six whole and four implied decimal digits. All inbound messages may be benignly re-sent, an order being identified by the RASH account and its day unique token. RASH 1.1 widened the stock symbol from 6 to 8 characters.

### Transport

SoupTCP or SoupBinTCP session: inbound messages travel as unsequenced data packets, outbound messages as sequenced data packets whose delivery and order the session guarantees.

### Key Characteristics

- **Fixed length ASCII** - Every message type has a fixed length of printable ascii characters
- **Routing and special handling** - Routing strategies, directed orders, discretion, pegging, random reserve and crosses
- **Benign resend** - Inbound messages are unsequenced and may be repeated without creating duplicates

