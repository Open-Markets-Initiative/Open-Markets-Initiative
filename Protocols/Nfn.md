## Nfn: NFN Data Service ascii message blocks

Message format of the Nasdaq Fund Network Data Service. Messages travel in blocks of at most 1000 seven bit ascii characters that open with SOH, separate messages with US and close with ETX. Each message is a 22 character header (message category, message type, session identifier, retransmission requester, message sequence number, originator id, date/time and test symbol flag) followed by a text section whose format and length depend on the message category and type.

### Overview

Alphabetic and alphanumeric fields are left justified and space filled, and numeric fields are right justified and zero filled, unless otherwise specified. Message categories are administrative (A), control (C) and NFN valuation (F) messages.

Retransmitted messages keep the original message sequence number and date/time, carry the requesting firm's two character retransmission requester in the header and are never mixed with current messages in the same block.

### Transport

Non-interactive simplex IP multicast on a primary and a back-up group whose messages are identical; each IP datagram carries one block.

### Key Characteristics

- **Ascii blocks** - Seven bit ascii blocks of up to 1000 characters delimited by SOH, US and ETX
- **Fixed header** - 22 character message header naming category, type and sequence number
- **Fixed width fields** - Alpha fields space filled on the right, numeric fields zero filled on the left

