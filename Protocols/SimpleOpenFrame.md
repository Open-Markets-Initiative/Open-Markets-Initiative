## SimpleOpenFrame: FIX SOFH framing used by CME iLink3 and BrokerTec

CME's adoption of the FIX Simple Open Framing Header (SOFH) for delimiting Simple Binary Encoding messages over TCP, providing a fixed-length length and encoding-type prefix that frames each SBE message on iLink3 order entry and BrokerTec fixed income trading sessions.

### Overview

SimpleOpenFrame is CME's implementation of FIX SOFH (Simple Open Framing Header), a FIX Trading Community standard designed to delimit messages encoded with any FIX-family encoding (FIX tag-value, FAST, FIXML, SBE) on stream transports. CME uses SOFH as the framing layer for its iLink3 order entry protocol and BrokerTec fixed income trading sessions, pairing it with SBE application payloads defined by CME-specific schemas.

The six-byte framing header carries only two fields: a four-byte message length (big-endian) that counts every byte of the frame including the header itself, and a two-byte encoding type that identifies the payload encoding and byte order. This minimal header lets the receiver size each message without inspecting the payload, stream arbitrary SBE templates over a single connection, and switch payload encodings within a session if required.

Session management for iLink3 and BrokerTec is provided by the FIX Performance Session Protocol (FIXP) carried inside the SOFH-framed SBE messages. SOFH itself is stateless — it performs no sequencing, authentication, or heartbeat function. Those responsibilities live in the application layer, leaving SOFH as a pure length-and-type delimiter with extremely low parsing overhead.

### Transport

SimpleOpenFrame sits directly on TCP and delimits each SBE-encoded application message with a six-byte prefix: a four-byte big-endian message length covering the entire frame and a two-byte encoding type identifying the payload format (for example, 0xEB50 denotes SBE 1.0 little-endian). Each read on the TCP socket yields one or more framed messages that can be parsed by length without delimiter scanning.

### Key Characteristics

- **FIX SOFH compliant** - Implements the FIX Trading Community Simple Open Framing Header standard
- **Six-byte prefix** - Four-byte length plus two-byte encoding type identifies each framed message
- **Length-prefixed** - Receivers size each message without delimiter scanning
- **Encoding type tag** - Two-byte encoding identifier signals the payload format and byte order per frame
- **Stateless** - No sequencing, authentication, or heartbeat — session concerns live above SOFH
- **SBE payload** - Frames SBE-encoded application messages on iLink3 and BrokerTec
- **iLink3 order entry** - Framing layer for CME's iLink3 session-oriented order entry protocol
- **BrokerTec trading** - Framing layer for BrokerTec fixed income and repo trading sessions

