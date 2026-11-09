## NeeqSecurities Order Entry: Neeq Order Entry

Binary order entry and trade reporting of the National Equities Exchange and Quotations, over a session to the trading gateway (BJTG) shared with the Beijing Stock Exchange. The interface currently serves spot bond trading on the fixed income platform, by matching through new orders and cancels and by negotiation through trade capture reports; the centralized auction, conversion, inquiry, subscription, put back, tender offer, refinancing securities lending, mutual trade confirmation, market making mutual trade confirmation, after hours block trade and quote businesses of the trading support platform are documented but not yet enabled.

### Overview

Every submission carries an ApplID naming the business. For a new order (101xxx) and a trade capture report (103xxx) the last three digits of the message type repeat it, while an order cancel request is always 102000. The gateway answers in kind, with 202xxx for an order response or successful cancel, 203xxx for a trade on an order, and 204xxx and 205xxx for a trade capture report acknowledgement and confirmation. The ApplID selects the extension fields that follow the common body.

A submission that fails a basic validity check, such as an unknown security code or a submission outside its time window, is refused with a Business Reject naming the rejected message's sequence number, type and business layer ID. One that passes is answered with execution reports or trade capture report responses.

Reports are numbered per platform partition. After logon the gateway sends a Platform State Info and a Platform Info giving the platform's partitions; the order management system then sends a Report Synchronization giving, per partition, the record number of the next report it expects, and the gateway resends from there. A Report Finished closes each partition's reports for the trading day.

Platforms open and close their businesses independently, so the order management system controls when it submits from the platform state and trading session status the gateway publishes. Only the fixed income platform currently publishes its trading session status.

### Transport

Standard point to point Tcp connection from the order management system to the trading gateway, which offers one trading port per platform; each port accepts one connection and each connection carries one session. A Logon establishes the session and the gateway confirms it with a Logon of its own, or refuses it with a Logout carrying a session status. Traffic is unencrypted, its security left to the participant's network. Each message carries the modulo 256 sum of its header and body in a trailing checksum.

### Key Characteristics

- **Session managed** - Logon, Logout and Heartbeat with a documented session status on refusal
- **Business keyed messages** - The ApplID in the last three digits of the message type selects the extension fields
- **Partitioned report recovery** - Reports numbered per platform partition and resent from a record number after logon
- **Trade capture reports** - Negotiated trades reported for matching, acknowledged and confirmed by the gateway
- **Per message checksum** - Each message carries the modulo 256 sum of its header and body
- **Unencrypted** - The gateway and the order management system share a secured network

