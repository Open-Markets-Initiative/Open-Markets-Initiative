## CboeFx Link Direct: Cboe Fx Low Latency Direct Order Entry

Low-latency binary order entry protocol for submitting forex orders directly to the Cboe Fx matching engine.

### Overview

Link Direct is the low-latency direct order entry interface to the Cboe Fx matching engine, providing market participants with a binary session-based protocol for submitting orders against spot and forward currency pairs. It is designed for high-frequency trading clients that need the lowest possible latency to the matching engine.

### Transport

Tcp for persistent authenticated Link Direct sessions carrying order submission, modification, cancellation, and execution report messages.

### Key Characteristics

- **Direct to matching engine** - Lowest latency order entry path on Cboe Fx
- **Forex order entry** - Spot and forward currency pair support
- **Session based** - Persistent authenticated Tcp session per client
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **High frequency** - Tuned for low latency trading workloads

