## Prm: Pre-Trade Risk Management

Nasdaq Nordic PRM Protocol, the fixed length binary wire format of the Pre-Trade Risk Management API that participants use to manage the configuration of their PRM Account on Inet Nordic.

### Overview

The PRM protocol is composed of logical messages passed between the PRM host and the client application. Every message has a fixed length and opens with a single character message type. Host messages are sequenced and their delivery is guaranteed by the lower level protocol; client messages are not, so every host bound message is designed to be resent benignly after a connection or application failure.

Alpha fields are left justified and padded on the right with spaces. Numeric fields are binary encoded big endian numbers in four widths: Longs of eight bytes, Integers of four, Shorts of two and Bytes of one. Timestamps are a single Long of nanoseconds since midnight Utc.

Optional fields that are not required are filled with -1 for an Integer or with ascii question marks for an Alpha, and the existing setting is then left unchanged, so sending every field in that form reads back the current configuration.

### Transport

PRM messages are carried over Tcp by a lower level protocol that guarantees delivery and sequencing of host messages, typically SoupBinTCP, with client messages in unsequenced data packets and host messages in sequenced data packets.

### Key Characteristics

- **Fixed length messages** - Each message type has one fixed layout opened by a single character type
- **Big endian** - Binary numbers of one, two, four or eight bytes in network byte order
- **Space padded alpha** - Alpha fields are left justified and padded on the right with spaces
- **Unchanged sentinels** - Optional fields sent as -1 or question marks keep the existing setting

