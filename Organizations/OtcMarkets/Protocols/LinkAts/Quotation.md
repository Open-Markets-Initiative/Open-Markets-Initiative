## LinkAts Quotation: OTC Link FIX Quotation Service — FIXIE Quote client interface

FIX quotation interface for OTC Link ATS, letting subscriber firms submit and manage dealer quotes electronically in the interdealer quotation system for OTCQX, OTCQB, and Pink securities. The client vocabulary is Quote, Quote Cancel, and TraderState inbound with Quote Acknowledgement and TraderState Acknowledgement outbound.

### Overview

FIXIE Quote is the FIX quotation service for OTC Link ATS, the interdealer quotation system and message routing and executions service for OTCQX, OTCQB, and Pink securities. Subscriber firms submit priced dealer quotes for the securities they trade; quotes from hundreds of participating broker-dealers across thousands of securities form the displayed OTC market.

The client message set is compact: Quote and Quote Cancel manage the firm's displayed quotations, and TraderState manages a trader's open/closed state. Each inbound message is confirmed by an acknowledgement (Quote Acknowledgement, TraderState Acknowledgement) carrying accept or reject status.

### Transport

Persistent authenticated FIX session over Tcp between the subscriber's OMS and OTC Link, carrying quote entry, quote cancel, and trader state messages with acknowledgements.

### Key Characteristics

- **Dealer quotation entry** - Electronic submission of priced dealer quotes into the OTC Link IDQS
- **Compact message set** - Quote, Quote Cancel, and TraderState with per-message acknowledgements
- **Trader state control** - TraderState opens and closes a trader's quoting across their securities
- **Full OTC tier coverage** - Quoting for OTCQX, OTCQB, and Pink securities
- **Companion trade service** - Pairs with the FIXIE Trade messaging service for negotiation and execution

