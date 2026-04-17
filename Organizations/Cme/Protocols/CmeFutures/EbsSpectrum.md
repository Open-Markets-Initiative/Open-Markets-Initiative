## CmeFutures Ebs Spectrum: Cme Ebs Spectrum Forex Order Entry

Binary order entry protocol for submitting orders on the Cme Ebs Spectrum spot foreign exchange trading platform.

### Overview

Ebs Spectrum is the Cme spot foreign exchange trading platform, offering electronic trading of major, minor, and emerging market currency pairs. The Ebs Spectrum order entry protocol provides participants with a binary session-based interface for submitting orders against the central limit order book and negotiating block trades.

The protocol is separate from Cme Globex order entry, reflecting the Fx trading workflow including credit checking, prime brokerage relationships, and the specific order types available on the Ebs venue.

### Transport

Tcp for persistent authenticated Ebs Spectrum sessions carrying order entry, modification, cancellation, and execution report messages for spot Fx currency pairs.

### Key Characteristics

- **Spot Fx** - Major, minor, and emerging market currency pairs
- **Ebs Spectrum venue** - Cme spot foreign exchange trading platform
- **Session based** - Persistent authenticated Tcp session per participant
- **Credit aware** - Pre-trade credit checking for bilateral counterparty relationships
- **Binary encoded** - Compact fixed-width messages for low latency

