## HkexSecurities Mmdh: Orion Market Data Cash Mainland Market Data Hub

Hkex Mainland Market Data Hub (MMDH) repackages the OMD-C Securities Standard (SS) and Index datafeed content for delivery to Mainland-China clients over TCP rather than the UDP multicast used by the central OMD-C system. The wire format is stream-oriented (no packet header) with a 20-byte per-message header carrying MsgLength, SeqNum, InternalSeqNum, and SendTime, followed by the MsgSize + MsgType payload prefix. Session management uses SendKey Diffie-Hellman key exchange, Logon with an encrypted password, and inline Refresh Request/Response recovery.

### Overview

MMDH is the TCP-delivered variant of the OMD-C Securities market data, scoped to the SS and Index tiers. The 20-byte message header replaces the UDP multicast packet header; SeqNum and InternalSeqNum support gap detection and intraday reconnect, and recovery is handled inline via Refresh Request/Response rather than a separate retransmission server.

### Transport

Point-to-point TCP delivery to a Mainland-hosted MMDH server with per-session sequencing (no UDP multicast); Primary and Secondary sites, active-active.

