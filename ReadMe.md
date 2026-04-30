[![Omi](https://github.com/Open-Markets-Initiative/Directory/blob/main/About/Images/Logo.png)](https://github.com/Open-Markets-Initiative/Directory/tree/main/About)

# The Open Markets Initiative

[![Organizations](https://img.shields.io/badge/Organizations-37-blue)](Organizations/) [![Protocols](https://img.shields.io/badge/Protocols-50-green)](Protocols/) [![Status](https://img.shields.io/badge/status-active-brightgreen)]() [![License](https://img.shields.io/badge/license-MIT-lightgrey)](About/License)

[The Open Markets Initiative](About/) (Omi) is a market-neutral effort to enhance the stability of electronic financial markets through transparency, modern tooling, and open documentation of the wire protocols that connect them.

This **Directory** is the catalog: a curated index of public protocol specifications, sample data, and reference material spanning **37 financial market organizations** and **50 wire protocols** — collected from publicly available sources and preserved here so the historical record survives even when exchanges retire or rename their feeds.

---

## Quick Navigation

| Section | What's there |
| --- | --- |
| [Organizations/](Organizations/) | One folder per exchange / venue / regulator — links, MICs, and per-protocol spec entry points |
| [Protocols/](Protocols/) | One markdown page per protocol — what it is, who runs it, encoding family, transport, and history |
| [Glossary/](Glossary/) | Common protocol concepts shared across venues |
| [Projects/](Projects/) | Index of related Omi GitHub repositories — code generators, dissectors, and research |
| [Research/](Research/) | Academic papers and patents on parser generation, low-latency systems, and binary protocols |
| [About/](About/) | Mission, philosophy, code of conduct, license |

---

## Coverage

**Organizations** span US/EU/APAC equities, options, futures, and OTC venues:

> 24X · A2X · Aquis · Asx · B3 · Boats · Box · BruceAts · Cboe · Cme · Coinbase · Currenex · Eurex · Euronext · Finra · Fix · Hkex · Ice · Iex · Imperative · Jnx · Jpx · Lse · Lseg · Memx · Miax · Nasdaq · Ndfex · NsxAustralia · Nyse · Odx · Omi · Otc · Siac · SmallX · Tmx · Txse

See the [organization table](Organizations/) for MICs and websites.

**Protocols** are categorized by role:

| Category | Protocols |
| --- | --- |
| Encoding | Boe3, Csm, Glimpse, iMpact, Obi, Rake, Sbe, T7, Ultra, Xdp |
| Framing | SimpleOpenFrame |
| Market Data | Amd, Apf, Ats, Cta, Dfi, Hsvf, Itch, Mach, Mitch, Omd, Pillar, Pitch, Xmt |
| Order Entry | Atp, Boe, Ouch, PillarStream, Sail, Seed |
| Protocol Suite | Bgw, BinaryEntryPoint, BinaryUmdf, Eobi, Eti, iLink3, Mdf, Mdp3, Opra |
| Session | CommonClient, SoupBinTcp |
| Transport | BinaryPacket, BinaryPacketHeader, IexTp, MoldUdp, MoldUdp64 |
| Trading | Cbp, Gtp |

See the [full protocol table](Protocols/) for descriptions.

---

## Related Omi Repositories

The Directory is the human-readable catalog. The machine-readable specifications live elsewhere and drive the source-generated artifacts:

**Specifications & Data**
- [omi-data-packets](https://github.com/Open-Markets-Initiative/omi-data-packets) — Sample packet captures keyed to the protocols listed here

**Source-Generated Outputs** *(driven from the specifications)*
- [wireshark-lua](https://github.com/Open-Markets-Initiative/wireshark-lua) — Wireshark dissectors in Lua
- [c-structs](https://github.com/Open-Markets-Initiative/c-structs) — C-style packed structs
- [CSharp.Packed.Structs](https://github.com/Open-Markets-Initiative/CSharp.Packed.Structs) — C# castable packed structs
- [omi.java.protocol.classes](https://github.com/Open-Markets-Initiative/omi.java.protocol.classes) — GC-friendly Java protocol classes

**Generators & Tooling**
- [Omi.Fix.Generators](https://github.com/Open-Markets-Initiative/Omi.Fix.Generators) — Composable FIX code generators
- [latency-lab](https://github.com/Open-Markets-Initiative/latency-lab) — Composable latency-measurement tools

**Reference Material**
- [omi-low-latency-reference](https://github.com/Open-Markets-Initiative/omi-low-latency-reference) — Low-latency programming articles
- [omi-markets-reference](https://github.com/Open-Markets-Initiative/omi-markets-reference) — Markets reference articles and links

A complete list lives in [Projects/](Projects/).

---

## Contributing

Documentation here is collected from publicly available sources. If you spot a stale link, a missing protocol version, or a venue we don't yet cover:

1. Open an issue describing the gap or correction.
2. Pull requests adding new organization / protocol entries are welcome — please follow the layout of an existing entry (see any folder under [Organizations/](Organizations/) for the template).
3. Read the [Code of Conduct](About/Conduct.md) before contributing.

---

## Philosophy

Omi is **market-neutral** — we do not take sides between exchanges, brokers, trading firms, or technology providers. We do, however, hold positions on two things:

- **Transparency.** Public protocol specifications and test data should remain public and discoverable, even after a feed is retired.
- **Best practices.** Source code in the Omi ecosystem follows automated builds, regression testing, clean code, and SOLID principles.

Read more in [About/](About/).

---

*Documentation sourced from publicly available materials. Specifications belong to their respective owners; this directory aggregates pointers and historical context only.*
