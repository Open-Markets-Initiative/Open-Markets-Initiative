## AquisStockExchange Snapshot: Aquis Stock Exchange snapshot market data

Snapshot feed of the Aquis Market Data (Amd) protocol, publishing every 10 seconds the full order book of each security traded on Aquis Stock Exchange via Ip multicast.

### Overview

Each snapshot starts with a Snapshot Start message naming the continuous stream's sequence number it was captured at, then for each security a Book Status message and a Book Entry message for each open order (section 2.2). The feed applies only to continuous trading.

### Transport

Ip multicast snapshot feed beside each market-split continuous feed, published at fixed 10 second intervals.

### Key Characteristics

- **Book snapshots** - Full book depth of each traded security every 10 seconds, for joining late or recovering from an outage

