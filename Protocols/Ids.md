## Ids: Information Dissemination System

Ascii market data encoding used by the Athens Exchange to disseminate the spot and derivatives markets of its Oasis trading system, framing each message between a Start Of Header character and a Longitudinal Redundancy Check byte around a thirty five character ascii header.

### Overview

The Information Dissemination System is the ascii dissemination of every instrument traded on the Athens Exchange Oasis platform. A Message Category in the header names which of the eighteen message types a packet carries and a Message Subcategory names the financial product, so one stream serves the securities and derivatives markets and every product on them, and every message is read by position rather than by tag.

Alpha fields are left justified and space filled, numeric fields right justified and zero filled, and a numeric field states its decimal places by the digit pattern the specification gives in prose rather than writing a point on the wire. The relaxed channel, which carries the Mifid II approved publication arrangement messages, uses the Esma field types instead, and those write their own decimal point.

Nothing on the wire carries a length. A packet is framed by its Start Of Header, its End Of Text and the Longitudinal Redundancy Check byte that follows the End Of Text, and the width of a body is what the Message Category implies.

### Transport

Tcp carries the feed, through the Internet Oriented Communication Portal, which also serves the recovery and retransmission requests a vendor makes by naming the first and last sequence numbers it wants.

### Key Characteristics

- **Ascii throughout** - Every field is printable ascii in Windows 1253, header and business content alike
- **Soh and Etx framed** - Each message sits between Start Of Header and End Of Text, with the redundancy check byte after the End Of Text
- **Category coded header** - A one character Message Category names the message and a one character Message Subcategory the financial product
- **Implied decimals** - Numeric fields state their decimal places by digit pattern, never writing a point
- **Venue coded** - A four character Market Identification Code in the header names the market publishing the packet
- **Sequenced with retransmission** - Every message but a line verification carries a sequence number recoverable by range

