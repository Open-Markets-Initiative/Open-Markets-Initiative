## Ntgi: Native Trading Gateway Interface

Proprietary binary order entry encoding developed by LSEG for the Millennium Exchange platform, carrying order and quote messages over a bidirectional Tcp session behind a four byte message header.

### Overview

Ntgi is the low latency binary alternative to the Fix trading gateway on Millennium Exchange, documented as MIT203. Where the Fix gateway carries tagged ASCII, Ntgi uses fixed width little endian fields at documented offsets, so a client can lay a structure directly over the received buffer.

The type system is small: signed and unsigned little endian integers, a Price carrying eight implied decimal places, ASCII Alpha characters, null terminated Strings, and single byte bit fields for the MiFID II flags. Reserved fields are padded with nulls and are expected to be ignored by receivers.

### Transport

Bidirectional Tcp session. Each message is framed by a Start of Message byte, a two byte length counting from the message type onwards, and a one byte message type. A separate recovery channel replays messages missed during a disconnect.

### Key Characteristics

- **Fixed width binary** - Documented offsets and lengths rather than tagged fields
- **Little endian** - All multi byte integers are little endian encoded
- **Bidirectional** - Client and server share the framing and several message types
- **Length framed** - A two byte length counting from the message type supports Tcp reassembly
- **Order entry** - Carries order and quote submission, amendment, cancellation and execution reporting

