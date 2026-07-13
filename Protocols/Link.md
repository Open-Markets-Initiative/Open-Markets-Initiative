## Link: OTC Markets shared binary market data encoding across all OTC Link and MOON ATS multicast feeds

Big-endian binary market data encoding used by every OTC Markets Group multicast feed — OTC Link ATS (daytime), OTC Link NQB (daytime IDQS), Overnight OTC (overnight IDQS), and MOON ATS (overnight NMS). Wire framing is uniform: 12-byte packet header (PacketSize, SeqNum, PacketFlag, Messages, PacketMilli) plus 3-byte per-message header (MessageSize, MessageType, payload). PacketFlag bit assignments (Heartbeat, SeqNumReset, Replay, Test) are shared across all four platforms. Products differ only in their message vocabulary and recovery-session shape.

### Overview

Link (Otc Link) is the shared binary encoding for OTC Markets Group's four multicast market data platforms. The packet framing, message framing, endianness, and packet flag bit layout are byte-identical across LinkAts (OTC Link ATS daytime), LinkNqb (OTC Link NQB daytime IDQS), Overnight (OTC Link Overnight OTC extended-hours), and MoonAts (MOON ATS overnight NMS). Products differ only in message vocabulary (which MessageType numbers they publish and what fields those messages carry) and in the shape of their recovery session.

The daytime OTC Link ATS product is quote-based: MessageTypes 1-8 carry Quote/Inside/Price Level/Reference Price events and their updates; 9 (Security), 11 (Start of Spin), 12 (End of Spin), 13 (Market Open), 14 (Market Close), 15-16 (Extended Security), 17 (Trade), 18 (Extended Trade). The extended-hours products (MoonAts, Overnight, LinkNqb) are order-based: MessageTypes 9 (Security), 11-12 (Start/End of Spin), 20 (Trading Session), 21-25 (Order Add/Update/Delete/Execution/Execution with Price), 26 (Trade), 27 (Top of Book), 28 (Imbalance). MessageTypes 9, 11, and 12 appear on both sides but carry different payloads.

PacketFlag bit assignments are unified: bit 0 Heartbeat, bit 1 SeqNumReset, bits 2-5 Reserved, bit 6 Replay, bit 7 Test. The daytime OTC Link ATS product publishes SeqNumReset, Replay, and Test packets; the extended-hours products currently only publish Heartbeat but consume the same bit layout via the shared PacketFlag struct definition in OtcMarkets.Udp.Source.xml.

### Transport

UDP multicast for real-time delivery of sequenced binary messages. Each packet carries a 12-byte packet header (PacketSize 2 + SeqNum 4 + PacketFlag 1 + Messages 1 + PacketMilli 4) followed by one or more messages concatenated in the packet, each framed by a 3-byte message header (MessageSize 2 + MessageType 1) followed by payload. All fields are big-endian, fixed-position, fixed-width. Redundant A/B multicast feeds published in parallel for arbitration. TCP recovery services vary by product family: OTC Link ATS daytime uses Replay Request / Resend Request Ack; MOON ATS, Overnight OTC, and OTC Link NQB use a session-based Retransmission service (Login, Retransmission Request/Response, Spin Request/Response, Enhanced Spin Request/Response, Heartbeat). The TCP wire framing itself — 3-byte message header + payload — is shared.

### Key Characteristics

- **Uniform packet framing** - 12-byte packet header (PacketSize 2 + SeqNum 4 + PacketFlag 1 + Messages 1 + PacketMilli 4) shared across all four platforms
- **Uniform message framing** - 3-byte message header (MessageSize 2 + MessageType 1) plus payload; MessageSize covers header + payload
- **Uniform PacketFlag bits** - Bit 0 Heartbeat, bit 1 SeqNumReset, bit 6 Replay, bit 7 Test; other bits Reserved
- **Big-endian fixed-width fields** - All numeric fields are big-endian; each field has a fixed length and fixed position within its message
- **Quote-based daytime vocabulary** - OTC Link ATS publishes Quote / Quote Update / Inside / Inside Update / Price Level / Reference Price / Security / Extended Security / Trade / Extended Trade messages on a single bundled multicast product
- **Order-based extended-hours vocabulary** - MOON ATS, Overnight OTC, and OTC Link NQB publish Order Add / Update / Delete / Execution / Execution with Price / Trade / Top of Book / Imbalance messages on separate Depth of Book and Top of Book channels
- **A/B multicast redundancy** - Every multicast product publishes redundant A and B feeds for arbitration and gap detection
- **Cross-platform reuse** - Byte-identical wire encoding published by OTC Link ATS (daytime), OTC Link NQB (daytime IDQS), Overnight OTC (overnight IDQS), and MOON ATS (overnight NMS ATS)

