## NasdaqCanada Order Entry: Nasdaq Canada Order Entry

Order entry protocols for the Nasdaq Canada CXC, CX2 and CXD trading books: the Ouch 5.0 native binary interface and the Fix 4.2 interface.

### Overview

Ouch 5.0 is the native low latency order entry protocol for Nasdaq Canada. Clients enter, replace and cancel orders over a SoupBin Tcp session, and the exchange acknowledges each request and reports the order lifecycle through accepted, replaced, canceled, executed, corrected and restated messages. Canadian regulatory attributes such as the Umir account type and user id are carried on every order, and the remaining order attributes travel in an optional tag value appendage.

The Fix 4.2 interface carries the same order functionality for firms that prefer a standard session protocol. One interface serves all three books: the destination book, or the smart order router, is chosen per order rather than per connection.

### Transport

Tcp session framed by SoupBin Tcp, with client requests carried in unsequenced data packets and exchange responses in sequenced data packets. Fix 4.2 order entry session with standard sequence number recovery through Resend Request and Sequence Reset.

### Key Characteristics

- **Order entry** - Enter, replace and cancel orders with full lifecycle reporting
- **Three books** - CXC, CX2 and CXD selected per order by destination
- **Tag value appendage** - Optional Ouch order attributes carried as tag value elements
- **Canadian regulatory fields** - Umir account type, user id and client identifier attributes

