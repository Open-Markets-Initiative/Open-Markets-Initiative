## Itac Enhanced Native Trading: Enhanced Native Trading Gateway

Native binary order entry gateway for the Johannesburg Stock Exchange Derivative and Bond Markets, supporting order management, quote management and intra-day instrument creation.

### Overview

The Enhanced Native Trading Gateway is one of the two native order entry interfaces the Johannesburg Stock Exchange offers on its Integrated Trading And Clearing platform. It serves the Derivative and Bond Markets, while the Basic Native Trading Gateway serves equity instruments of the Jse and Nsx markets. Clients submit orders, cancellations, mass cancellations and amendments, and may request the creation of instruments intra-day through the Security Definition Request.

The wire format is the Millennium native gateway encoding: every message opens with a four byte header carrying a start of message byte fixed at binary two, a little endian message length counted from the message type field onwards, and a one byte message type. Three native trading servers are available per gateway instance, each exposing a Real-Time channel and a Recovery channel, with missed messages recovered by sequence number per matching partition.

### Transport

Tcp session carrying length prefixed native messages. Each server exposes two channels specified separately: a Real-Time channel for order submission and live updates, and a Recovery channel that replays server initiated messages missed while a client was disconnected.

### Key Characteristics

- **Derivatives and bonds** - Serves the Jse Derivative and Bond Markets rather than equities
- **Intra-day instrument creation** - Security Definition Request allows clients to create instruments during the trading day
- **Millennium native encoding** - Four byte message header with little endian binary fields
- **Partitioned recovery** - Missed messages replayed by sequence number per matching partition on a dedicated Recovery channel
- **Eight decimal prices** - Price fields are eight byte signed little endian integers with eight implied decimal places

