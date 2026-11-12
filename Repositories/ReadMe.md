[![Omi](https://github.com/Open-Markets-Initiative/Open-Markets-Initiative/raw/main/About/Images/Logo.png)](https://github.com/Open-Markets-Initiative/Open-Markets-Initiative/tree/main/About)

# Omi Repositories

Index of repositories under the [Open Markets Initiative](https://github.com/Open-Markets-Initiative) GitHub organization.

---

## Source Generated Languages

Code-generated artifacts produced from the protocol specifications.

### C#

| Repository | Description |
| --- | --- |
| [omi-csharp-protocols][omi-csharp-protocols] | Source generated C# protocol parsers, fixed-layout structs and immutable classes |
| [CSharp.Sequential.Layout][CSharp.Sequential.Layout] | Source generated castable C# binary protocol packed structs |
| [CSharp.Hft.Structs][CSharp.Hft.Structs] | High performance C# binary protocol ref structs |
| [Omi.CSharp.Parsers][Omi.CSharp.Parsers] | Source generated high performance C# parsers for common exchange protocols |

### Rust

| Repository | Description |
| --- | --- |
| [omi-rust-protocols][omi-rust-protocols] | Zero-copy Rust message views, one crate per protocol version |

### C++

| Repository | Description |
| --- | --- |
| [omi-cpp-protocols][omi-cpp-protocols] | Source generated C++ protocol parsers and utilities |
| [omi-cpp-formats][omi-cpp-formats] | Source generated C++ translations for formats like JSON and Parquet |
| [omi-cpp-databases][omi-cpp-databases] | Source generated C++ programs that load packet captures into databases |
| [cpp-packets][cpp-packets] | High performance inline modern C++ packet parsing |
| [cpp-parsers][cpp-parsers] | Source generated C++ exchange parsers |
| [omi-cpp-exchanges][omi-cpp-exchanges] | Source generated C++ exchange simulators: order entry gateway, matching engine, feed publishers and snapshot servers |
| [omi-cpp-protocol-statistics][omi-cpp-protocol-statistics] | Code generated executables that gather statistics and gap detection on common exchange protocols |
| [omi-cpp-parquet-wide][omi-cpp-parquet-wide] | Code generated Apache Parquet protocol transforms for common exchange protocols |

### Java

| Repository | Description |
| --- | --- |
| [omi-java-protocols][omi-java-protocols] | Garbage-collector friendly Java binary protocol classes |

### Python

| Repository | Description |
| --- | --- |
| [omi-python-classes][omi-python-classes] | Stable Python deserialization for common exchange protocols |

## Generated Definitions

Domain specific language definitions

| Repository | Language | Description |
| --- | --- | --- |
| [omi-kaitai-struct-definitions][omi-kaitai-struct-definitions] | Ksy | Kaitai Struct definitions for common exchange binary protocols |
| [omi-dfdl-definitions][omi-dfdl-definitions] | Dfdl | Data Format Description Language schemas for common exchange protocols |
| [omi-p4-definitions][omi-p4-definitions] | P4 | P4 definitions for common exchange protocols for software and hardware data planes |
| [omi-fix-dictionaries][omi-fix-dictionaries] | Xml | FIX protocol dictionaries (QuickFIX-format XML, one per FIX version) |
| [omi-spicy-definitions][omi-spicy-definitions] | Spicy | Spicy grammars for common exchange binary protocols, for the Spicy toolchain and Zeek |
| [omi-lean4-definitions][omi-lean4-definitions] | Lean | Lean 4 definitions of common exchange binary protocols, with proofs |
| [omi-rocq-definitions][omi-rocq-definitions] | Rocq | Rocq Prover definitions of common exchange binary protocols, with proofs |
| [omi-tlaplus-definitions][omi-tlaplus-definitions] | TLA+ | TLA+ definitions of common exchange binary protocols, model checked with TLC |
| [omi-promela-definitions][omi-promela-definitions] | Promela | Promela definitions of common exchange binary protocols, model checked with Spin |
| [omi-xml-specifications][omi-xml-specifications] | Xml | XML specifications for common exchange protocols |

## Telemetry

Source generated protocol dissectors for packet capture analysis and network monitoring.

| Repository | Language | Description |
| --- | --- | --- |
| [omi-wireshark-lua][omi-wireshark-lua] | Lua | Source generated cross platform Wireshark dissectors |
| [omi-wireshark-c][omi-wireshark-c] |  | Source generated Wireshark dissectors in C, built in to Wireshark |

## Reference Material

Curated knowledge bases and historical context.

| Repository | Description |
| --- | --- |
| [Open-Markets-Initiative][Open-Markets-Initiative] | General information about The Open Markets Initiative — the catalog you are reading |
| [omi-low-latency-reference][omi-low-latency-reference] | Knowledge base for low latency programming |
| [omi-markets-reference][omi-markets-reference] | Knowledge base for market data collection and analysis |

## Production Sample Data

Example protocol data captures from production feeds.

| Repository | Description |
| --- | --- |
| [omi-data-packets][omi-data-packets] | Example protocol data captures |
| [omi-data-pcaps][omi-data-pcaps] | Exchange pcaps for automated testing |

## Esoteric Languages

Exchange protocols generated into esoteric programming languages.

| Repository | Language | Description |
| --- | --- | --- |
| [omi-esoteric-languages][omi-esoteric-languages] | Brainfuck | Source generated Brainfuck decoders, session handshakes and matching engines for common exchange protocols |

---

*Full org listing: [github.com/Open-Markets-Initiative](https://github.com/Open-Markets-Initiative)*


[omi-csharp-protocols]: https://github.com/Open-Markets-Initiative/omi-csharp-protocols "Source generated C# protocol parsers, fixed-layout structs and immutable classes"
[omi-rust-protocols]: https://github.com/Open-Markets-Initiative/omi-rust-protocols "Zero-copy Rust message views, one crate per protocol version"
[omi-cpp-protocols]: https://github.com/Open-Markets-Initiative/omi-cpp-protocols "Source generated C++ protocol parsers and utilities"
[omi-cpp-formats]: https://github.com/Open-Markets-Initiative/omi-cpp-formats "Source generated C++ translations for formats like JSON and Parquet"
[omi-cpp-databases]: https://github.com/Open-Markets-Initiative/omi-cpp-databases "Source generated C++ programs that load packet captures into databases"
[cpp-packets]: https://github.com/Open-Markets-Initiative/cpp-packets "High performance inline modern C++ packet parsing"
[cpp-parsers]: https://github.com/Open-Markets-Initiative/cpp-parsers "Source generated C++ exchange parsers"
[omi-cpp-exchanges]: https://github.com/Open-Markets-Initiative/omi-cpp-exchanges "Source generated C++ exchange simulators: order entry gateway, matching engine, feed publishers and snapshot servers"
[omi-cpp-protocol-statistics]: https://github.com/Open-Markets-Initiative/omi-cpp-protocol-statistics "Code generated executables that gather statistics and gap detection on common exchange protocols"
[omi-cpp-parquet-wide]: https://github.com/Open-Markets-Initiative/omi-cpp-parquet-wide "Code generated Apache Parquet protocol transforms for common exchange protocols"
[CSharp.Sequential.Layout]: https://github.com/Open-Markets-Initiative/CSharp.Sequential.Layout "Source generated castable C# binary protocol packed structs"
[CSharp.Hft.Structs]: https://github.com/Open-Markets-Initiative/CSharp.Hft.Structs "High performance C# binary protocol ref structs"
[Omi.CSharp.Parsers]: https://github.com/Open-Markets-Initiative/Omi.CSharp.Parsers "Source generated high performance C# parsers for common exchange protocols"
[omi-java-protocols]: https://github.com/Open-Markets-Initiative/omi-java-protocols "Garbage-collector friendly Java binary protocol classes"
[omi-python-classes]: https://github.com/Open-Markets-Initiative/omi-python-classes "Stable Python deserialization for common exchange protocols"
[omi-kaitai-struct-definitions]: https://github.com/Open-Markets-Initiative/omi-kaitai-struct-definitions "Kaitai Struct definitions for common exchange binary protocols"
[omi-dfdl-definitions]: https://github.com/Open-Markets-Initiative/omi-dfdl-definitions "Data Format Description Language schemas for common exchange protocols"
[omi-p4-definitions]: https://github.com/Open-Markets-Initiative/omi-p4-definitions "P4 definitions for common exchange protocols for software and hardware data planes"
[omi-fix-dictionaries]: https://github.com/Open-Markets-Initiative/omi-fix-dictionaries "FIX protocol dictionaries (QuickFIX-format XML, one per FIX version)"
[omi-spicy-definitions]: https://github.com/Open-Markets-Initiative/omi-spicy-definitions "Spicy grammars for common exchange binary protocols, for the Spicy toolchain and Zeek"
[omi-lean4-definitions]: https://github.com/Open-Markets-Initiative/omi-lean4-definitions "Lean 4 definitions of common exchange binary protocols, with proofs"
[omi-rocq-definitions]: https://github.com/Open-Markets-Initiative/omi-rocq-definitions "Rocq Prover definitions of common exchange binary protocols, with proofs"
[omi-tlaplus-definitions]: https://github.com/Open-Markets-Initiative/omi-tlaplus-definitions "TLA+ definitions of common exchange binary protocols, model checked with TLC"
[omi-promela-definitions]: https://github.com/Open-Markets-Initiative/omi-promela-definitions "Promela definitions of common exchange binary protocols, model checked with Spin"
[omi-xml-specifications]: https://github.com/Open-Markets-Initiative/omi-xml-specifications "XML specifications for common exchange protocols"
[omi-wireshark-lua]: https://github.com/Open-Markets-Initiative/omi-wireshark-lua "Source generated cross platform Wireshark dissectors"
[omi-wireshark-c]: https://github.com/Open-Markets-Initiative/omi-wireshark-c "Source generated Wireshark dissectors in C, built in to Wireshark"
[Open-Markets-Initiative]: https://github.com/Open-Markets-Initiative/Open-Markets-Initiative "General information about The Open Markets Initiative — the catalog you are reading"
[omi-low-latency-reference]: https://github.com/Open-Markets-Initiative/omi-low-latency-reference "Knowledge base for low latency programming"
[omi-markets-reference]: https://github.com/Open-Markets-Initiative/omi-markets-reference "Knowledge base for market data collection and analysis"
[omi-data-packets]: https://github.com/Open-Markets-Initiative/omi-data-packets "Example protocol data captures"
[omi-data-pcaps]: https://github.com/Open-Markets-Initiative/omi-data-pcaps "Exchange pcaps for automated testing"
[omi-esoteric-languages]: https://github.com/Open-Markets-Initiative/omi-esoteric-languages "Source generated Brainfuck decoders, session handshakes and matching engines for common exchange protocols"
