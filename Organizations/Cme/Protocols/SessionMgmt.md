## SessionMgmt: Cme Market Data Session Management

Sbe-encoded session management protocol for authenticated market data subscriptions on Cme Group platforms.

### Overview

The Cme Session Management protocol provides session-level authentication and subscription management for Cme market data feeds. It enables clients to negotiate authenticated sessions using Hmac-Sha-256 signatures, subscribe to market data for specific instruments or security groups, and manage subscription lifecycle including snapshot requests and unsubscription.

The protocol supports Negotiate/NegotiateResponse handshakes with access key authentication, MarketDataRequest messages for subscribing to specific instruments by security group, and Terminate messages for session cleanup. Subscription requests can request snapshots only, snapshots with ongoing updates, or unsubscription from previous subscriptions.

### Transport

Tcp with Sbe-encoded messages. Session establishment via Negotiate message with Hmac-Sha-256 authentication using AccessKeyId and Uuid.

### Key Characteristics

- **Hmac-Sha-256 authentication** - Cryptographic session authentication with access key and signature
- **Sbe encoded** - Fixed-position, fixed-length fields with little-endian byte ordering
- **Subscription management** - Subscribe to snapshots, snapshot+updates, or unsubscribe
- **Security group filtering** - Subscribe to market data by security group
- **Partial acknowledgement** - Subscription scope can be fully or partially acknowledged
- **Uuid session identity** - Sessions identified by Uuid recommended as microsecond Unix timestamp
