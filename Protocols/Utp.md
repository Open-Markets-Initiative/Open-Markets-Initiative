## Utp: Unlisted Trading Privileges binary feed encoding

Utp is the binary wire encoding used by the Unlisted Trading Privileges plan to disseminate consolidated quotation (UQDF) and trade (UTDF) data for Nasdaq-listed securities. Big-endian fixed-length fields with a one-byte message-category dispatch.

### Transport

UTP feeds are distributed as multicast UDP via MoldUDP64; subscribers detect gaps and recover via retransmission services.

### Key Characteristics

- **Binary encoding** - Fixed-length fields with big-endian byte ordering for efficient parsing
- **Sequenced messages** - Each message carries a sequence number for gap detection and recovery
- **Unidirectional** - Data flows from the SIP to the subscriber (dissemination only)

