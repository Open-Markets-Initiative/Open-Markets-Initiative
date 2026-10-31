## MemxEquities Instrument Directory: MEMX equities instrument directory file

MEMX equities instrument directory, a comma delimited file of every security MEMX trades: its security ID, CMS root and suffix, round lot, test flag and minimum price variation.

### Overview

The first line is a header row naming the columns, each following line one security, its columns separated by a comma and its text columns quoted.

The columns are the MEMOIR Depth Feed's Instrument Directory message (MEMOIR Depth Feed v1.3, section 5.1) as text: SecurityID, Symbol, SymbolSfx, RoundLot, IsTestSymbol and MPV. MEMX uses CMS symbology, a root and suffix combination.

### Transport

MEMXInstrumentDirectory.csv, served without a login from www.memxtrading.com/files/.

### Key Characteristics

- **Reference file** - A file, not a live feed; the MEMOIR feeds send the same directory as Instrument Directory messages at the start of each day

