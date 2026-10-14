## DxeDerivatives Binary Order Entry: Cboe Europe Derivatives Binary Order Entry

Cboe Binary Order Entry (Boe) protocol for submitting, modifying, and cancelling orders, quotes, complex instruments and trade reports on Cboe Europe Derivatives (MIC CEDX), specified in the CEDX BOE2 Specification.

### Overview

Binary Order Entry is the native order entry interface for Cboe Europe Derivatives, the Cboe European futures and options venue. It uses the Boe2 message header and return bitfield model of the Cboe Europe equities BOE2 specification, extended with quotes, complex instruments, cross orders and trade capture reports for derivatives.

### Transport

Tcp via the Cboe Boe session layer for persistent authenticated order flow with sequence tracking and heartbeats.

### Key Characteristics

- **Cboe Boe** - Native Cboe Binary Order Entry protocol
- **European derivatives** - Index and single stock futures and options
- **Session based** - Persistent authenticated Tcp session per member
- **Optional fields** - Input and return bitfields select the optional fields each message carries

