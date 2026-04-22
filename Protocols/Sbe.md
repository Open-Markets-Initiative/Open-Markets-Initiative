## Sbe: Simple Binary Encoding

Fix Simple Binary Encoding a high performance wire format for Fix protocol messages using fixed width binary fields optimized for low latency encoding and decoding.

### Overview

Simple Binary Encoding (SBE) is a FIX Trading Community standard that defines a binary wire format for encoding financial protocol messages. It was designed as a replacement for the FIX tag-value and FAST encoding schemes, targeting the performance requirements of modern electronic trading where nanosecond-level encoding and decoding latency is critical. SBE achieves this through a schema-driven approach where message layouts are fully described in XML template files, allowing both encoders and decoders to operate on fixed-position, fixed-length fields without delimiters, length prefixes, or sequential parsing.

The encoding standard is part of the broader FIX Performance initiative alongside the FIX Performance Session Protocol (FIXP). SBE defines the application layer encoding while FIXP handles session management. SBE messages consist of a message header (containing schema ID, version, template ID, and block length), followed by root-level fixed fields, optional repeating groups, and variable-length data fields.

SBE has been widely adopted across global exchanges including CME Group (MDP3, iLink3), B3 (UMDF, BinaryEntryPoint), Euronext (Optiq), MEMX (Memoir), Coinbase, and others. Reference implementations exist in C, C++, Java, C#, Go, Rust, and Python.

### Key Characteristics

- **Zero-copy capable** - Fixed-position fields allow direct memory access without deserialization into intermediate objects
- **Schema driven** - XML message templates define all message layouts, field types, offsets, and semantic metadata
- **Deterministic size** - Fixed-length root blocks and group entries enable precise buffer allocation
- **Code generation** - Encoders and decoders generated from XML schemas in multiple programming languages
- **Backward compatible** - Schema versioning allows receivers to decode messages from older schema versions
- **No field delimiters** - Fields are accessed by position and length, eliminating parsing overhead
- **FIX semantic layer** - Field IDs and message types align with FIX application-level semantics
- **Little-endian default** - Native byte ordering for x86/x64 architectures minimizes byte-swap overhead

