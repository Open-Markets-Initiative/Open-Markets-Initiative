## Itac Basic Native Trading: Basic Native Trading Gateway

Native binary order entry gateway for the equity instruments of the Johannesburg Stock Exchange and the National Stock Exchange of Australia markets, supporting order management, pegged orders and internal crosses.

### Overview

The Basic Native Trading Gateway is one of the two native order entry interfaces the Johannesburg Stock Exchange offers on its Integrated Trading And Clearing platform. It serves equity instruments of the Jse and Nsx markets, while the Enhanced Native Trading Gateway serves the Derivative and Bond Markets. Alongside ordinary order management it carries pegged orders, an end of day volume auction uncross, and the New Order Cross message for internal crosses.

The wire format is the Millennium native gateway encoding: every message opens with a four byte header carrying a start of message byte fixed at binary two, a little endian message length counted from the message type field onwards, and a one byte message type. The platform supports two protocol versions concurrently, selected by the Protocol Version field of the Logon rather than carried per message, and the newer version appends a Self Trade Prevention Key to the New Order and Execution Report messages.

### Transport

Tcp session carrying length prefixed native messages. Each server exposes two channels specified separately: a Real-Time channel for order submission and live updates, and a Recovery channel that replays server initiated messages missed while a client was disconnected.

### Key Characteristics

- **Equities** - Serves equity instruments of the Jse and Nsx markets rather than derivatives
- **Pegged orders** - Pegged and Pegged Limit order types pegged to mid, bid or offer
- **Internal crosses** - New Order Cross carries both sides of an internal cross in one message
- **Session negotiated versioning** - Two protocol versions supported concurrently, selected at Logon
- **Millennium native encoding** - Four byte message header with little endian binary fields

