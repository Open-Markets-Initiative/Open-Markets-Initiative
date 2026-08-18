## Omd: Orion Market Data

Hkex Orion Market Data platform encoding, shared across the Securities (OMD-C), China Connect (OMD-CC), and Derivatives (OMD-D) market data feeds and the Mainland Market Data Hub (MMDH). The UDP multicast feeds share a 16-byte packet header and differ only in the semantics of byte 3, captured as two packet-header versions: v1 (Derivatives) uses a Compression Mode indicator supporting optional payload compression; v2 (Securities and China Connect) uses a plain Filler byte with no payload compression. A third TCP header version, v3 (MMDH), replaces the multicast packet header with a stream-oriented 20-byte per-message session header for Mainland-China delivery. Individual feed identity (product tier, market segment) is carried by the Exchange and Protocol axes, not the encoding.

### Overview

OMD is the family brand for Hkex's binary market data feeds. Every OMD feed publishes a 16-byte packet header (PktSize, MsgCount, byte-3 mode/filler, SeqNum, SendTime) followed by variable-length messages framed by a 4-byte header (MsgSize, MsgType). The two wire-format variants differ only in whether byte 3 signals payload compression (v1, OMD-D) or is a reserved filler (v2, OMD-C and OMD-CC).

### Transport

Real-time multicast on dual A/B channels with per-channel sequence numbers. Retransmission and refresh recovery services.

