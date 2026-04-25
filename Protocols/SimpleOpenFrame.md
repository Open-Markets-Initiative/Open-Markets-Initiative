## SimpleOpenFrame: FIX-standard length and encoding-type prefix for stream transports

FIX Trading Community standard for delimiting messages encoded with any FIX-family encoding (FIX tag-value, FIXML, FAST, SBE) on stream transports. A six-byte prefix carries a four-byte big-endian message length and a two-byte encoding-type identifier so receivers can size each frame without inspecting the payload.

### Overview

The Simple Open Framing Header (SOFH) is a FIX Trading Community standard designed to provide a minimal, encoding-agnostic message delimiter for FIX messages carried over stream transports. SOFH solves the framing problem that arises when binary FIX-family encodings (most notably SBE) are sent over TCP: receivers need to know where one message ends and the next begins without inspecting the payload, and they may need to recognise multiple payload encodings on the same connection.

The header carries only two fields: a four-byte message length in big-endian (network) byte order that counts every byte of the frame including the header, and a two-byte encoding type identifying the payload encoding and byte order. This keeps SOFH stateless and extremely cheap to parse, with framing overhead independent of payload size or schema.

SOFH has been widely adopted across global venues that use SBE for low-latency order entry and market data, including CME (iLink3 order entry, BrokerTec fixed-income trading), B3 (BinaryEntryPoint order entry across equities and derivatives), Euronext Optiq, and others. Session-layer concerns (sequencing, authentication, heartbeats, recovery) are handled by the FIX Performance Session Protocol (FIXP) carried inside the SOFH-framed messages — SOFH itself performs no session function.

### Transport

SOFH sits directly on TCP and delimits each FIX-family encoded message with a six-byte prefix: a four-byte big-endian message length covering the entire frame including the header, and a two-byte encoding type identifying the payload format and byte order (for example, 0xEB50 denotes SBE 1.0 little-endian). Each TCP read yields one or more framed messages parseable by length without delimiter scanning.

### Key Characteristics

- **FIX Trading Community standard** - Open specification published and maintained by the FIX Trading Community
- **Six-byte prefix** - Four-byte length plus two-byte encoding type identifies each framed message
- **Length-prefixed** - Receivers size each message without delimiter scanning
- **Encoding-agnostic** - Two-byte encoding type lets a single connection carry multiple FIX-family payload encodings
- **Stateless** - No sequencing, authentication, or heartbeat — session concerns live above SOFH (typically FIXP)
- **Big-endian length** - Frame length uses network byte order regardless of payload byte order
- **SBE companion** - Standard framing layer for SBE-encoded messages over TCP
- **Wide adoption** - Used by CME iLink3 and BrokerTec, B3 BinaryEntryPoint, Euronext Optiq, and other global venues

