## Omd: Orion Market Data

Hkex Orion Market Data platform umbrella encoding. Two wire-format variants share the same 16-byte packet header structure but differ in the semantics of byte 3: v1 (OMD-D) uses Compression Mode; v2 (OMD-C and OMD-CC) uses a plain Filler byte with no payload compression. The full per-family message sets and product tiers live under Omdc, Omdd, and Omdcc encodings; the shared Omd encoding is used only for cross-family artefacts such as gap-detection observability dissectors.

### Overview

OMD is the family brand for Hkex's binary market data feeds. Every OMD feed publishes a 16-byte packet header (PktSize, MsgCount, byte-3 mode/filler, SeqNum, SendTime) followed by variable-length messages framed by a 4-byte header (MsgSize, MsgType). The two wire-format variants differ only in whether byte 3 signals payload compression (v1, OMD-D) or is a reserved filler (v2, OMD-C and OMD-CC).

### Transport

Real-time multicast on dual A/B channels with per-channel sequence numbers. Retransmission and refresh recovery services.

