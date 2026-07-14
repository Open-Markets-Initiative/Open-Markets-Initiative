## LinkAts Trade Messaging: OTC Link FIX Messaging Service — FIXIE Trade client interface

FIX trade messaging interface for OTC Link ATS, carrying dealer-to-dealer trade negotiation and execution for OTC securities. Subscriber firms exchange New Trade, Fill, Cancel, Decline, Counter, and Replace trade messages to negotiate against displayed quotes, with support for Quote Access Payments, MAX messages, and Best Execution Instructions.

### Overview

FIXIE Trade is the FIX messaging service for OTC Link ATS trade negotiation. A dealer initiates with a New Trade message against a counterparty's displayed quote; the counterparty responds with Fill, Decline, or Counter, and negotiations proceed through Counter and Replace messages until filled, cancelled, or declined. Trade message state, message ids, and execution id/execute time conventions track each negotiation's lifecycle.

The service supports Quote Access Payments (QAP), MAX messages, Best Execution Instructions (BXI), and OTC Link negotiations with replace semantics. Executed trades feed the OTC Feed trade data and volume feed.

### Transport

Persistent authenticated FIX session over Tcp between the subscriber's OMS and OTC Link, routing trade negotiation messages between counterparty broker-dealers.

### Key Characteristics

- **Dealer-to-dealer negotiation** - New Trade, Fill, Cancel, Decline, Counter, and Replace trade messages
- **Negotiation lifecycle state** - Trade message state, message ids, and execution id/execute time conventions
- **Quote Access Payments** - QAP terms carried on trade messages between counterparties
- **Best Execution Instructions** - BXI attributes qualifying handling and execution obligations
- **Trade data feed** - Executed trades disseminate via the OTC Feed trade data and volume feed
- **Companion quote service** - Pairs with the FIXIE Quote quotation service for displayed markets

