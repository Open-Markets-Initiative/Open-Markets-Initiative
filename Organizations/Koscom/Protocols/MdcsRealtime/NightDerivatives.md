## MdcsRealtime Night Derivatives: Koscom Market Data Service Realtime Night Derivatives product feed

Koscom-to-subscriber realtime market data output feed for the KRX derivatives night session of the Market Data Service (MDCS), publishing KRX market activity as Exture ASCII fixed-width records over UDP multicast with two-level TR-CODE dispatch. Wire format, message set and TR codes are identical to the Derivatives A day feed; the night session is distributed by a separate MDCS instance and carries Market ID NDV.

### Transport

UDP multicast for real-time delivery of Exture ASCII fixed-width records, one message per datagram, framed by a 2-byte Data Category + 3-byte Information Category TR-CODE prefix and a 0xFF end-of-text sentinel, served from the night production port band 13xxx rather than the day band 10xxx. TCP retransmission service for gap recovery; subscribers detect gaps via Data Category-specific sequencing and request replay from the retransmission endpoint.

### Key Characteristics

- **Night derivatives session feed** - KRX derivatives night session, 18:00 to 06:00 the next day, trading the 10 most liquid derivatives products under Market ID NDV
- **Identical wire format to the day feed** - Same message set, layouts and TR codes as MDCS Realtime Derivatives A; night data is distinguished by Market ID NDV and the night Product IDs, not by any format difference
- **Separate night distribution instance** - Served by its own MDCS instance on production port band 13xxx; the day channel table documents only the 10xxx, 11xxx, 12xxx and 20xxx bands
- **Night disclosure serial range** - Emergency disclosures raised by the night system are sent as F0 text records with an annual disclosure serial in the 975000 to 980000 range

