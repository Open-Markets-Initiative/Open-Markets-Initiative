## Hsvf: Box Options Sola Multicast Market Data

High speed vendor feed distributing real-time options quotes, trades, and session events for contracts traded on the Box Options Exchange using the Sola Hsvf format.

### Overview

Hsvf is the Box Options Exchange implementation of the Sola High Speed Vendor Feed, providing market data subscribers with real-time quotes, trades, and session events for options listed on Box. All messages that comprise the Box Hsvf feed are transmitted on a dedicated line with each message type fixed in format, enabling efficient parsing and low processing overhead.

The protocol covers the full set of events needed to track options markets including security definitions, trading status, underlying instrument changes, and quote and trade messages, along with session-level messages such as schedule notifications. Re-transmission of any data is available on the transmission line for subscribers that need to recover missed messages.

### Transport

Udp multicast delivery of fixed-format Hsvf messages for real-time options quote and trade dissemination on a dedicated transmission line. Tcp for the unicast Hsvf service used for re-transmission requests and subscriber recovery of missed messages.

### Key Characteristics

- **Options market data** - Quotes and trades for options contracts on Box
- **Sola Hsvf** - Sola platform High Speed Vendor Feed implementation
- **Fixed format** - Each message type has a fixed format for efficient parsing
- **Multicast delivery** - Real-time delivery on a dedicated transmission line
- **Re-transmission** - Recovery service for missed messages
- **Session events** - Schedule notifications and trading status updates included in the feed

