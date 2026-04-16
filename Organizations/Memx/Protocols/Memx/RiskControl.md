## Risk Control: Memx Pre Trade Risk Configuration

Binary protocol used by risk administrators to configure and query pre-trade risk limits for clearing firms, sponsoring broker-dealers, and sponsored participants on the Members Exchange.

### Overview

Memx Risk Control is the binary protocol used by clearing firms and sponsoring broker-dealers to manage pre-trade risk limits for their sponsored participants on the Members Exchange. The protocol allows administrators to set, update, and query limits on metrics such as notional exposure, order rate, and open position, with changes taking effect in real time against the matching engine risk checks.

The wire format uses Simple Binary Encoding consistent with the other Memx protocols, and the session is carried over an authenticated Tcp connection. Inline risk validation in the Memo order entry path uses the limits maintained through this interface, so updates propagate immediately to all subsequent order submissions from the impacted participants.

### Transport

Tcp for authenticated risk administrator sessions carrying limit set, limit query, and limit update messages between the client and the Memx risk engine.

### Key Characteristics

- **Pre-trade risk** - Limit management for clearing firms and sponsored participants
- **Sbe encoded** - Simple Binary Encoding consistent with other Memx protocols
- **Real-time propagation** - Updates apply immediately to the matching engine risk checks
- **Authenticated session** - Tcp session reserved for risk administrators
- **Limit set and query** - Configure new limits and read current limits
- **Integrated with Memo** - Same limits enforced by the inline risk checks on the order entry path

