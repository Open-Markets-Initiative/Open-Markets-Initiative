## Order Service: Currenex Forex Ouch Order Entry

Ouch-based order entry service for submitting, replacing, and cancelling forex orders on the Currenex trading platform.

### Overview

Currenex Order Service is the order entry protocol for the Currenex forex platform, providing market participants with a high-performance binary interface to submit, modify, and cancel orders against Executable Streaming Prices received from market makers. The wire format is a Currenex subset of the Ouch protocol with fixed-width binary messages optimized for low-latency processing.

With the number of order messages growing significantly year over year, the Order Service is tuned for high-performance processing and networking so that trading latency remains consistent under rising message volumes. The protocol carries the full order lifecycle including new orders, order replacements, cancellations, execution reports, and rejects, delivered over a persistent authenticated Tcp session.

### Transport

Tcp for persistent authenticated Ouch sessions carrying inbound order entry, replace, and cancel messages and outbound execution reports and acknowledgements.

### Key Characteristics

- **Ouch encoded** - Compact fixed-width binary message format for low latency
- **Forex order entry** - Order submission against Executable Streaming Prices
- **Full order lifecycle** - New, replace, cancel, execution report, and reject messages
- **Session based** - Persistent authenticated Tcp session per participant
- **High performance** - Tuned for rising order message volumes year over year
- **Currenex platform** - Designed for direct participants on the Currenex venue

