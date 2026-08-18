## MainlandMarketDataHub Combined: Orion Market Data Cash Mainland Market Data Hub

TCP real-time securities and index market data feed for the Hkex Mainland Market Data Hub. Covers session-management messages (SendKey, Logon, Logon Response, Logout), inline refresh messages (Refresh Request, Refresh Response, Refresh Complete), and the full OMD-C SS + Index payload message set (Market/Security/Liquidity/Currency Rate reference; Trading Session and Security Status; VCM Trigger; Odd Lot Add/Delete; Aggregate Order Book Update; Broker Queue; Order Imbalance; Trade Ticker; Closing/Nominal/IEP/Reference prices; Statistics/Market Turnover/Yield; News; Index Definition and Data; Stock Connect Daily Quota Balance and Market Turnover).

### Overview

MMDH is a TCP-only alternative to OMD-C multicast for Mainland-China clients. Payload message codes match OMD-C SS + Index; the wire framing uses a 20-byte per-message header carrying MsgLength, SeqNum, InternalSeqNum, and SendTime with no packet-level header.

### Transport

TCP/IP session to a Mainland-hosted MMDH server.

