[![Omi](https://github.com/Open-Markets-Initiative/Directory/blob/main/About/Images/Logo.png)](https://github.com/Open-Markets-Initiative/Directory/tree/main/About)

# Omi Projects

Index of repositories under the [Open Markets Initiative](https://github.com/Open-Markets-Initiative) GitHub organization.

---

## Reference Material

Curated knowledge bases and historical context.

| Repository | Description |
| --- | --- |
| [Directory][Directory] | General information about The Open Markets Initiative — the catalog you are reading |
| [omi-low-latency-reference][omi-low-latency-reference] | Knowledge base for low latency programming |
| [omi-markets-reference][omi-markets-reference] | Knowledge base for market data collection and analysis |

## Production Sample Data

Example protocol data captures from production feeds.

| Repository | Description |
| --- | --- |
| [omi-data-packets][omi-data-packets] | Example protocol data captures |
| [omi-data-pcaps][omi-data-pcaps] | Exchange pcaps for automated testing |

## Dictionaries

Machine-readable protocol format dictionaries.

| Repository | Language | Description |
| --- | --- | --- |
| [omi-fix-dictionaries][omi-fix-dictionaries] | Xml | FIX protocol dictionaries (QuickFIX-format XML, one per FIX version) |
| [omi-kaitai-struct-definitions][omi-kaitai-struct-definitions] | Ksy | Kaitai Struct definitions for common exchange binary protocols |
| [omi-dfdl-definitions][omi-dfdl-definitions] | Dfdl | Data Format Description Language schemas for common exchange protocols |

## Source Generated Outputs

Code-generated artifacts produced from the protocol specifications.

| Repository | Language | Description |
| --- | --- | --- |
| [wireshark-lua][wireshark-lua] | Lua | Source generated cross platform Wireshark dissectors |
| [c-structs][c-structs] | C | Source generated binary protocol c-style packed structs |
| [omi-csharp-protocols][omi-csharp-protocols] | C# | Source generated C# protocol parsers, fixed-layout structs and immutable classes |
| [omi-rust-protocols][omi-rust-protocols] | Rust | Zero-copy Rust message views, one crate per protocol version |
| [cpp-packets][cpp-packets] | C++ | High performance inline modern C++ packet parsing |
| [cpp-parsers][cpp-parsers] | C++ | Source generated C++ exchange parsers |
| [omi-cpp-protocol-statistics][omi-cpp-protocol-statistics] | C++ | Code generated executables that gather statistics and gap detection on common exchange protocols |
| [omi-cpp-parquet-wide][omi-cpp-parquet-wide] | C++ | Code generated Apache Parquet protocol transforms for common exchange protocols |
| [CSharp.Sequential.Layout][CSharp.Sequential.Layout] | C# | Source generated castable C# binary protocol packed structs |
| [CSharp.Hft.Structs][CSharp.Hft.Structs] | C# | High performance C# binary protocol ref structs |
| [Omi.CSharp.Parsers][Omi.CSharp.Parsers] | C# | Source generated high performance C# parsers for common exchange protocols |
| [omi.java.protocol.classes][omi.java.protocol.classes] | Java | Garbage-collector friendly Java binary protocol classes |
| [omi-python-classes][omi-python-classes] | Python | Stable Python deserialization for common exchange protocols |

## Generators and Tooling

The composable toolchain that drives the generated outputs above.

| Repository | Description |
| --- | --- |
| [Omi.Fix.Generators][Omi.Fix.Generators] | Composable FIX source generators |
| [Omi.Fix.Fast.Generators][Omi.Fix.Fast.Generators] | Code generation for FIX FAST protocols |
| [latency-lab][latency-lab] | Composable tools for automating latency measurement and reporting |
| [hpcap][hpcap] | High performance pcap traversal |
| [omi-pcap-to-json][omi-pcap-to-json] | Optimized pcap to JSON converters |

---

*Full org listing: [github.com/Open-Markets-Initiative](https://github.com/Open-Markets-Initiative)*


[Directory]: https://github.com/Open-Markets-Initiative/Directory "General information about The Open Markets Initiative — the catalog you are reading"
[omi-low-latency-reference]: https://github.com/Open-Markets-Initiative/omi-low-latency-reference "Knowledge base for low latency programming"
[omi-markets-reference]: https://github.com/Open-Markets-Initiative/omi-markets-reference "Knowledge base for market data collection and analysis"
[omi-data-packets]: https://github.com/Open-Markets-Initiative/omi-data-packets "Example protocol data captures"
[omi-data-pcaps]: https://github.com/Open-Markets-Initiative/omi-data-pcaps "Exchange pcaps for automated testing"
[omi-fix-dictionaries]: https://github.com/Open-Markets-Initiative/omi-fix-dictionaries "FIX protocol dictionaries (QuickFIX-format XML, one per FIX version)"
[omi-kaitai-struct-definitions]: https://github.com/Open-Markets-Initiative/omi-kaitai-struct-definitions "Kaitai Struct definitions for common exchange binary protocols"
[omi-dfdl-definitions]: https://github.com/Open-Markets-Initiative/omi-dfdl-definitions "Data Format Description Language schemas for common exchange protocols"
[wireshark-lua]: https://github.com/Open-Markets-Initiative/wireshark-lua "Source generated cross platform Wireshark dissectors"
[c-structs]: https://github.com/Open-Markets-Initiative/c-structs "Source generated binary protocol c-style packed structs"
[omi-csharp-protocols]: https://github.com/Open-Markets-Initiative/omi-csharp-protocols "Source generated C# protocol parsers, fixed-layout structs and immutable classes"
[omi-rust-protocols]: https://github.com/Open-Markets-Initiative/omi-rust-protocols "Zero-copy Rust message views, one crate per protocol version"
[cpp-packets]: https://github.com/Open-Markets-Initiative/cpp-packets "High performance inline modern C++ packet parsing"
[cpp-parsers]: https://github.com/Open-Markets-Initiative/cpp-parsers "Source generated C++ exchange parsers"
[omi-cpp-protocol-statistics]: https://github.com/Open-Markets-Initiative/omi-cpp-protocol-statistics "Code generated executables that gather statistics and gap detection on common exchange protocols"
[omi-cpp-parquet-wide]: https://github.com/Open-Markets-Initiative/omi-cpp-parquet-wide "Code generated Apache Parquet protocol transforms for common exchange protocols"
[CSharp.Sequential.Layout]: https://github.com/Open-Markets-Initiative/CSharp.Sequential.Layout "Source generated castable C# binary protocol packed structs"
[CSharp.Hft.Structs]: https://github.com/Open-Markets-Initiative/CSharp.Hft.Structs "High performance C# binary protocol ref structs"
[Omi.CSharp.Parsers]: https://github.com/Open-Markets-Initiative/Omi.CSharp.Parsers "Source generated high performance C# parsers for common exchange protocols"
[omi.java.protocol.classes]: https://github.com/Open-Markets-Initiative/omi.java.protocol.classes "Garbage-collector friendly Java binary protocol classes"
[omi-python-classes]: https://github.com/Open-Markets-Initiative/omi-python-classes "Stable Python deserialization for common exchange protocols"
[Omi.Fix.Generators]: https://github.com/Open-Markets-Initiative/Omi.Fix.Generators "Composable FIX source generators"
[Omi.Fix.Fast.Generators]: https://github.com/Open-Markets-Initiative/Omi.Fix.Fast.Generators "Code generation for FIX FAST protocols"
[latency-lab]: https://github.com/Open-Markets-Initiative/latency-lab "Composable tools for automating latency measurement and reporting"
[hpcap]: https://github.com/Open-Markets-Initiative/hpcap "High performance pcap traversal"
[omi-pcap-to-json]: https://github.com/Open-Markets-Initiative/omi-pcap-to-json "Optimized pcap to JSON converters"
