## Sqf: Specialized Quote Interface (SQF)

Nasdaq Specialized Quote Interface binary wire format for options market maker quoting: fixed layout big endian messages identified by a two character Type/Subtype, carried over SoupBinTCP.

### Overview

SQF messages begin with a two character message type (Type/Subtype); request and reply pairs typically differ only by the case of the second character. Integer fields are unsigned big endian binary, prices are signed integers with an implied scale of 4 (Price) or 6 (Price6), and alphanumeric fields are left justified and space padded.

### Transport

SQF operates over TCP using the SoupBinTCP session layer, which provides login, heartbeats, sequenced delivery with recovery for sequenced messages and best-effort delivery for unsequenced messages.

### Key Characteristics

- **Binary encoding** - Fixed layout big endian messages
- **Two character message types** - Type/Subtype identifies every message
- **Session management** - SoupBinTCP login, heartbeat and sequencing

