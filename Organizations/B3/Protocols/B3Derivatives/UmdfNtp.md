## B3Derivatives Umdf Ntp: B3 Fix/Fast Multicast Market Data, legacy per channel templates

Fast-encoded multicast market data in the organisation B3 published before the per message templates, declaring a separate incremental refresh template for each channel so that a channel's book updates decode against a dictionary of their own.

### Overview

These are the templates-UMDF-NTP files B3 keeps among the previous versions of its FIX/FAST templates. Where the current files declare one incremental refresh template for the whole feed, these declare one per channel group - equity futures, interest rate futures, options, the ePRS open interest and settlement feed - so a receiver subscribing to a single channel decodes against a template and a dictionary dedicated to it.

B3 retains two of these files, both heading themselves FILE VERSION 5.0.1: the 2011-11-24 file as NTP ONLY TEMPLATE and the 2018-08-20 file as PUMA ONLY TEMPLATE. The version the vendor states does not distinguish them, so each specification carries the publication year in its build segment.

### Transport

Udp multicast carrying one or more messages per datagram, each a ten byte unencoded technical header then a Fast encoded Fix message.

### Key Characteristics

- **Fast encoded** - Fix Adapted for Streaming 1.1 templates, the same dialect the current files use
- **Per channel templates** - A separate incremental refresh template for each channel group rather than one for the feed
- **Per template dictionaries** - Each template declares its own dictionary, so operator state never crosses channels
- **Technical header** - Ten byte unencoded preamble per message holding sequence number, chunk count, chunk index and payload length
- **Superseded** - Retained by B3 among its previous template versions rather than published as current

