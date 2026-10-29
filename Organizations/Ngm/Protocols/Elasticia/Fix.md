## Elasticia Fix: Elasticia FIX Protocol

The main protocol for communicating with the Nordic Growth Market trading system: Fix Latest application messages over Fixt 1.1 sessions, offering an order entry service for orders, quotes and trade reports and a market data service for market data and reference data, encoded as Fix tag value or as Fast 1.1.

### Overview

Nordic Growth Market sends a Fast stream as blocks of one message each, every block preceded by its size in bytes, which the exchange encodes as a four byte overlong unsigned integer as Fast 1.1 allows.

The templates are static, so a change to them is a protocol change, and each is mapped to its Fix message by application type, the Fix message name, with each field's Fix tag as its Fast auxiliary identifier. Shared components such as the standard header, the security reference and the parties block are templates without ids that message templates include by static reference; dynamic template references are not used.

The order entry and market data services share one set of templates, and message filtering lets a user limit which messages a service sends or receives.

### Transport

Tcp carries both services; when Fast encoded, Fast Session Control Protocol 1.1 level 2 runs as a thin layer on top, with its hello, alert and reset messages.

### Key Characteristics

- **Fix Latest** - Application messages from Fix Latest over Fixt 1.1 session messages
- **Fast 1.1 or tag value** - Either encoding is supported on the same protocol
- **Session control protocol** - Fast Scp 1.1 level 2 manages Fast sessions and dictionary resets
- **Sized blocks** - One message per block behind a four byte overlong block size
- **Static templates** - Component templates without ids included by static reference

